## TempAR

### Description

TempAR by raing3 is a mod of NitePR which was updated to support PSPAR and CWCheat code types as well as additional
code types inspired by NitroHax for the DS.

### Code types

<table>
    <tr>
        <th>Type</th>
        <th>Description</th>
    </tr>
    <tr><th colspan="2">Conditional 32-bit Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0x03</code><br />
            <code>Greater Than</code><br />
            <code>3XXXXXXX YYYYYYYY</code>
        </td>
        <td>Same as PSPAR engine except if lowest bit of address is set the offset is added to the address.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x04</code><br />
            <code>Less Than</code><br />
            <code>4XXXXXXX YYYYYYYY</code>
        </td>
        <td>Same as PSPAR engine except if lowest bit of address is set the offset is added to the address.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x05</code><br />
            <code>Equal To</code><br />
            <code>5XXXXXXX YYYYYYYY</code>
        </td>
        <td>Same as PSPAR engine except if lowest bit of address is set the offset is added to the address.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x06</code><br />
            <code>Not Equal To</code><br />
            <code>6XXXXXXX YYYYYYYY</code>
        </td>
        <td>Same as PSPAR engine except if lowest bit of address is set the offset is added to the address.</td>
    </tr>
    <tr><th colspan="2">Conditional 16-bit + Masking Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0x07</code><br />
            <code>Greater Than</code><br />
            <code>7XXXXXXX ZZZZYYYY</code>
        </td>
        <td>Same as PSPAR engine except if lowest bit of address is set the offset is added to the address.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x08</code><br />
            <code>Less Than</code><br />
            <code>8XXXXXXX ZZZZYYYY</code>
        </td>
        <td>Same as PSPAR engine except if lowest bit of address is set the offset is added to the address.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x09</code><br />
            <code>Equal To</code><br />
            <code>9XXXXXXX ZZZZYYYY</code>
        </td>
        <td>Same as PSPAR engine except if lowest bit of address is set the offset is added to the address.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0A</code><br />
            <code>Not Equal To</code><br />
            <code>AXXXXXXX ZZZZYYYY</code>
        </td>
        <td>Same as PSPAR engine except if lowest bit of address is set the offset is added to the address.</td>
    </tr>
    <tr><th colspan="2">Data Register Codes</th></tr>
    <tr>
        <td>
            <code>Type 0xD4</code><br />
            <code>Dx Data Operation</code><br />
            <code>D400000Y XXXXXXXX</code>
        </td>
        <td>Sets the 'Dx data register' to Data = <code>? XXXXXXXX</code> where ? is determined by <code>Y</code> as follows:<br />0 - add<br />1 - or<br />2 - and<br />3 - xor<br />4 - logical shift left<br />5 - logical shift right<br />6 - rotate right<br />7 - arithmetic shift right<br />8 - multiply</td>
    </tr>
    <tr><th colspan="2">Miscellaneous Codes</th></tr>
    <tr>
        <td>
            <code>Type 0xC1</code><br />
            <code>Call Function with Arguments</code><br />
            <code>C100000Y XXXXXXXX</code><br />
            <code>AAAAAAAA BBBBBBBB</code><br />
            <code>CCCCCCCC DDDDDDDD</code>
        </td>
        <td>Performs a jal to the function at <code>XXXXXXXX</code>. The number of arguments to pass to the function is specified by <code>Y</code>.<br />a0 = <code>0xAAAAAAAA</code><br />a1 = <code>0xBBBBBBBB</code><br />a2 = <code>0xCCCCCCCC</code><br />a3 = <code>0xDDDDDDDD</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xC2</code><br />
            <code>Run Code From Cheat List</code><br />
            <code>C2000000 XXXXXXXX</code>
        </td>
        <td>Performs a jal to the function directly after the <code>0xC2</code> code line. The length of function is specified by <code>XXXXXXXX</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xC5</code><br />
            <code>Counter</code><br />
            <code>C5000000 ZZZZYYYY</code>
        </td>
        <td>Checks if <code>YYYY</code> == (not <code>ZZZZ</code> < cheat apply count).<br />If not, the code(s) following this one are not executed (ie. execution status is set to false) until a code type <code>D0</code> or <code>D2</code> is encountered, or until the end of the code list is reached.</td>
    </tr>
</table>

### Fake addresses

Fake address are used to return system information which either can't be accessed from memory or does not have a
static address. These are intended to simplify the process of cheat creation / conversion from other cheat devices.

Presently these addresses can only be accessed using the exact address listed
(ie. no 8/16-bit retrieval of the upper return bits).

<table>
    <tr>
        <th>Address</th>
        <th>Return Value</th>
    </tr>
    <tr>
        <td>0x0A000000</td>
        <td>Pressed buttons. See <a href="../other/button-activators.md">button activators</a> for possible values.</td>
    </tr>
    <tr>
        <td>0x0A000004</td>
        <td>X-axis of analog nub.</td>
    </tr>
    <tr>
        <td>0x0A000008</td>
        <td>Y-axis of analog nub.</td>
    </tr>
</table>