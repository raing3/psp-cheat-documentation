## PSP Action Replay (PSPAR)

### Description

PSP Action Replay is the first commercial cheat device for the PSP. The first PSPAR (released October 2008) used the
Pandora exploit to launch the software on PSP-1000 and early PSP-2000 consoles. A newer version released in
December 2009 used a signed binary installed in the UPDATE folder and launched directly from the XMB.

### Code types

<table>
    <tr>
        <th>Type</th>
        <th>Description</th>
    </tr>
    <tr><th colspan="2">Constant RAM Writes</th></tr>
    <tr>
        <td>
            <code>Type 0x00</code><br />
            <code>32-bit</code><br />
            <code>0XXXXXXX YYYYYYYY</code>
        </td>
        <td>Writes word <code>YYYYYYYY</code> to <code>[XXXXXXX+offset]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x01</code><br />
            <code>16-bit</code><br />
            <code>1XXXXXXX 0000YYYY</code>
        </td>
        <td>Writes halfword <code>YYYY</code> to <code>[XXXXXXX+offset]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x02</code><br />
            <code>8-bit</code><br />
            <code>2XXXXXXX 000000YY</code>
        </td>
        <td>Writes byte <code>YY</code> to <code>[XXXXXXX+offset]</code>.</td>
    </tr>
    <tr><th colspan="2">Conditional 32-bit Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0x03</code><br />
            <code>Greater Than</code><br />
            <code>3XXXXXXX YYYYYYYY</code>
        </td>
        <td>Checks if <code>YYYYYYYY</code> > (word at <code>[XXXXXXX]</code> or <code>[offset]</code> if <code>[XXXXXXX]</code> is 0)<br />If not, the code(s) following this one are not executed (ie. execution status is set to false) until a code type <code>D0</code> or <code>D2</code> is encountered, or until the end of thecode list is reached.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x04</code><br />
            <code>Less Than</code><br />
            <code>4XXXXXXX YYYYYYYY</code>
        </td>
        <td>Checks if <code>YYYYYYYY</code> < (word at <code>[XXXXXXX]</code> or <code>[offset]</code> if <code>[XXXXXXX]</code> is 0)<br />If not, the code(s) following this one are not executed (ie. execution status is set to false) until a code type <code>D0</code> or <code>D2</code> is encountered, or until the end of thecode list is reached.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x05</code><br />
            <code>Equal To</code><br />
            <code>5XXXXXXX YYYYYYYY</code>
        </td>
        <td>Checks if <code>YYYYYYYY</code> == (word at <code>[XXXXXXX]</code> or <code>[offset]</code> if <code>[XXXXXXX]</code> is 0)<br />If not, the code(s) following this one are not executed (ie. execution status is set to false) until a code type <code>D0</code> or <code>D2</code> is encountered, or until the end of thecode list is reached.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x06</code><br />
            <code>Not Equal To</code><br />
            <code>6XXXXXXX YYYYYYYY</code>
        </td>
        <td>Checks if <code>YYYYYYYY</code> != (word at <code>[XXXXXXX]</code> or <code>[offset]</code> if <code>[XXXXXXX]</code> is 0)<br />If not, the code(s) following this one are not executed (ie. execution status is set to false) until a code type <code>D0</code> or <code>D2</code> is encountered, or until the end of thecode list is reached.</td>
    </tr>
    <tr><th colspan="2">Conditional 16-bit + Masking Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0x07</code><br />
            <code>Greater Than</code><br />
            <code>7XXXXXXX ZZZZYYYY</code>
        </td>
        <td>Checks if <code>YYYY</code> > (not <code>ZZZZ</code> < halfword at <code>[XXXXXXX]</code> or <code>[offset]</code> if <code>[XXXXXXX]</code> is 0).<br />If not, the code(s) following this one are not executed (ie. execution status is set to false) until a code type <code>D0</code> or <code>D2</code> is encountered, or until the end of the code list is reached.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x08</code><br />
            <code>Less Than</code><br />
            <code>8XXXXXXX ZZZZYYYY</code>
        </td>
        <td>Checks if <code>YYYY</code> < (not <code>ZZZZ</code> < halfword at <code>[XXXXXXX]</code> or <code>[offset]</code> if <code>[XXXXXXX]</code> is 0).<br />If not, the code(s) following this one are not executed (ie. execution status is set to false) until a code type <code>D0</code> or <code>D2</code> is encountered, or until the end of the code list is reached.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x09</code><br />
            <code>Equal To</code><br />
            <code>9XXXXXXX ZZZZYYYY</code>
        </td>
        <td>Checks if <code>YYYY</code> == (not <code>ZZZZ</code> < halfword at <code>[XXXXXXX]</code> or <code>[offset]</code> if <code>[XXXXXXX]</code> is 0).<br />If not, the code(s) following this one are not executed (ie. execution status is set to false) until a code type <code>D0</code> or <code>D2</code> is encountered, or until the end of the code list is reached.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0A</code><br />
            <code>Not Equal To</code><br />
            <code>AXXXXXXX ZZZZYYYY</code>
        </td>
        <td>Checks if <code>YYYY</code> != (not <code>ZZZZ</code> < halfword at <code>[XXXXXXX]</code> or <code>[offset]</code> if <code>[XXXXXXX]</code> is 0).<br />If not, the code(s) following this one are not executed (ie. execution status is set to false) until a code type <code>D0</code> or <code>D2</code> is encountered, or until the end of the code list is reached.</td>
    </tr>
    <tr><th colspan="2">Offset Codes</th></tr>
    <tr>
        <td>
            <code>Type 0x0B</code><br />
            <code>Load Offset</code><br />
            <code>BXXXXXXX 00000000</code>
        </td>
        <td>Loads the 32-bit value into the 'offset'.<br />Offset = word at <code>[XXXXXXX+offset]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xC4</code><br />
            <code>Safe Data Store</code><br />
            <code>C4000000 XXXXXXXX</code>
        </td>
        <td>Sets the offset value to point to the first word of this code. Storing data at offset+0x4 will save over the top of <code>XXXXXXXX</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xC6</code><br />
            <code>Write Offset</code><br />
            <code>C6000000 XXXXXXXX</code>
        </td>
        <td>Writes the offset value to <code>[XXXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xD3</code><br />
            <code>Set Offset</code><br />
            <code>D3000000 XXXXXXXX</code>
        </td>
        <td>Sets the offset value to <code>XXXXXXXX</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xDC</code><br />
            <code>Add Offset</code><br />
            <code>DC000000 XXXXXXXX</code>
        </td>
        <td>Adds <code>XXXXXXXX</code> to the current offset (Dual Offset).</td>
    </tr>
    <tr><th colspan="2">Loop Codes</th></tr>
    <tr>
        <td>
            <code>Type 0x0C</code><br />
            <code>C0000000 YYYYYYYY</code>
        </td>
        <td>This sets the 'Dx repeat value' to <code>YYYYYYYY</code> and saves the 'Dx nextcode to be executed' and the 'Dx execution status'. Repeat will be executed when a <code>D1</code>/<code>D2</code> code is encountered.<br />When repeat is executed, the AR reloads the 'next code to be executed' and the 'execution status' from the Dx registers.</td>
    </tr>
    <tr><th colspan="2">Terminator Codes</th></tr>
    <tr>
        <td>
            <code>Type 0xD0</code><br />
            <code>Terminator</code><br />
            <code>D0000000 00000000</code>
        </td>
        <td>Loads the previous execution status. If none exists, the execution status stays at 'execute codes'.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xD1</code><br />
            <code>Loop Execute Variant</code><br />
            <code>D1000000 00000000</code>
        </td>
        <td>Executes the next block of codes 'n' times (specified by the <code>0x0C</code> codetype), but doesn't clear the Dx register upon completion.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xD2</code><br />
            <code>Loop Execute Variant / Full Terminator</code><br />
            <code>D2000000 00000000</code>
        </td>
        <td>Executes the next block of codes 'n' times (specified by the <code>0x0C</code> codetype), and clears all temporary data. (i.e. execution status, offsets, code C settings, etc.)<br />This code can also be used as a full terminator, giving the same effects to any block of code.</td>
    </tr>
    <tr><th colspan="2">Data Register Codes</th></tr>
    <tr>
        <td>
            <code>Type 0xD4</code><br />
            <code>Add Value</code><br />
            <code>D4000000 XXXXXXXX</code>
        </td>
        <td>Adds <code>XXXXXXXX</code> to the 'Dx data register'.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xD5</code><br />
            <code>Set Value</code><br />
            <code>D5000000 XXXXXXXX</code>
        </td>
        <td>Set <code>XXXXXXXX</code> to the 'Dx data register'.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xD6</code><br />
            <code>32-bit Incrementive Write</code><br />
            <code>D6000000 XXXXXXXX</code>
        </td>
        <td>Writes the 'Dx data register' word to <code>[XXXXXXXX+offset]</code>, and increments the offset by 4.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xD7</code><br />
            <code>16-bit Incrementive Write</code><br />
            <code>D7000000 XXXXXXXX</code>
        </td>
        <td>Writes the 'Dx data register' halfword to <code>[XXXXXXXX+offset]</code>, and increments the offset by 2.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xD8</code><br />
            <code>8-bit Incrementive Write</code><br />
            <code>D8000000 XXXXXXXX</code>
        </td>
        <td>Writes the 'Dx data register' byte to <code>[XXXXXXXX+offset]</code>, and increments the offset by 1.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xD9</code><br />
            <code>32-bit Load</code><br />
            <code>D9000000 XXXXXXXX</code>
        </td>
        <td>Loads the word at <code>[XXXXXXXX+offset]</code> and stores it in the'Dx data register'.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xDA</code><br />
            <code>16-bit Load</code><br />
            <code>DA000000 XXXXXXXX</code>
        </td>
        <td>Loads the halfword at <code>[XXXXXXXX+offset]</code> and stores it in the'Dx data register'.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xDB</code><br />
            <code>8-bit Load</code><br />
            <code>DB000000 XXXXXXXX</code>
        </td>
        <td>Loads the byte at <code>[XXXXXXXX+offset]</code> and stores it in the'Dx data register'.</td>
    </tr>
    <tr><th colspan="2">Miscellaneous Codes</th></tr>
    <tr>
        <td>
            <code>Type 0x0E</code><br />
            <code>Patch Code</code><br />
            <code>EXXXXXXX YYYYYYYY</code>
        </td>
        <td>Copies <code>YYYYYYYY</code> bytes from directly after the <code>0xE</code> code line to <code>[XXXXXXXX+offset]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0F</code><br />
            <code>Memory Copy Code</code><br />
            <code>FXXXXXXX YYYYYYYY</code>
        </td>
        <td>Copy <code>YYYYYYYY</code> bytes from offset to <code>XXXXXXX</code> (<code>XXXXXXX</code> is fixed, no offsets are added to it).</td>
    </tr>
    <tr><th colspan="2">Folder/Comment Codes</th></tr>
    <tr>
        <td>
            <code>Type 0xCF</code><br />
            <code>Single Select Folder</code><br />
            <code>CF000000 XXXXXXXX</code>
        </td>
        <td>Sets the cheat as a single select folder and the next <code>XXXXXXXX</code> items (codes, folders and comments) will be subitems of the current item.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xCF</code><br />
            <code>Comment</code><br />
            <code>CF000001 XXXXXXXX</code>
        </td>
        <td>Sets the cheat as a comment and the next <code>XXXXXXXX</code> items will also be treated as comments.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0xCF</code><br />
            <code>Multi Select Folder</code><br />
            <code>CF000002 XXXXXXXX</code>
        </td>
        <td>Sets the cheat as a folder and the next <code>XXXXXXXX</code> items (codes, folders and comments) will be subitems of the current item.</td>
    </tr>
</table>
