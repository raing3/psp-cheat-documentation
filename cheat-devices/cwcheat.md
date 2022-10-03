## CWCheat

### Description

CWCheat by weltall was the first universal cheat device for the PSP. Inspired by the PS2 Action Replay code types
this cheat device also supports native PS1 Action Replay codes and homebrew software.

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
            <code>8-bit</code><br />
            <code>0XXXXXXX YYYYYYYY</code>
        </td>
        <td>Writes byte <code>YY</code> to <code>[XXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x01</code><br />
            <code>16-bit</code><br />
            <code>1XXXXXXX 0000YYYY</code>
        </td>
        <td>Writes halfword <code>YYYY</code> to <code>[XXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x02</code><br />
            <code>32-bit</code><br />
            <code>2XXXXXXX 000000YY</code>
        </td>
        <td>Writes word <code>YYYYYYYY</code> to <code>[XXXXXXX]</code>.</td>
    </tr>
    <tr><th colspan="2">Increment and Decrement Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0x03</code><br />
            <code>8-bit Increment</code><br />
            <code>301000YY XXXXXXXX</code>
        </td>
        <td>Adds <code>YY</code> to the byte stored at <code>[XXXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x03</code><br />
            <code>16-bit Increment</code><br />
            <code>3030YYYY XXXXXXXX</code>
        </td>
        <td>Adds <code>YYYY</code> to the halfword stored at <code>[XXXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x03</code><br />
            <code>32-bit Increment</code><br />
            <code>30500000 XXXXXXXX</code><br />
            <code>YYYYYYYY 000000000</code>
        </td>
        <td>Adds <code>YYYYYYYY</code> to the word stored at <code>[XXXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x03</code><br />
            <code>8-bit Decrement</code><br />
            <code>302000YY XXXXXXXX</code>
        </td>
        <td>Subtracts <code>YY</code> from the byte stored at <code>[XXXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x03</code><br />
            <code>16-bit Decrement</code><br />
            <code>3040YYYY XXXXXXXX</code>
        </td>
        <td>Subtracts <code>YYYY</code> from the halfword stored at <code>[XXXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x03</code><br />
            <code>32-bit Decrement</code><br />
            <code>30600000 XXXXXXXX</code><br />
            <code>YYYYYYYY 000000000</code>
        </td>
        <td>Subtracts <code>YYYYYYYY</code> from the word stored at <code>[XXXXXXXX]</code>.</td>
    </tr>
    <tr><th colspan="2">Conditional Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>8-bit Equal To</code><br />
            <code>DXXXXXXX 200000YY</code>
        </td>
        <td>Checks if <code>YY</code> == (byte at <code>[XXXXXXX]</code>).<br />If not, the following line is not executed (ie. execution status is set to false for 1 line).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>8-bit Not Equal To</code><br />
            <code>DXXXXXXX 201000YY</code>
        </td>
        <td>Checks if <code>YY</code> != (byte at <code>[XXXXXXX]</code>).<br />If not, the following line is not executed (ie. execution status is set to false for 1 line).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>8-bit Less Than</code><br />
            <code>DXXXXXXX 202000YY</code>
        </td>
        <td>Checks if <code>YY</code> < (byte at <code>[XXXXXXX]</code>).<br />If not, the following line is not executed (ie. execution status is set to false for 1 line).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>8-bit Greater Than</code><br />
            <code>DXXXXXXX 203000YY</code>
        </td>
        <td>Checks if <code>YY</code> > (byte at <code>[XXXXXXX]</code>).<br />If not, the following line is not executed (ie. execution status is set to false for 1 line).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>16-bit Equal To</code><br />
            <code>DXXXXXXX 0000YYYY</code>
        </td>
        <td>Checks if <code>YYYY</code> == (halfword at <code>[XXXXXXX]</code>).<br />If not, the following line is not executed (ie. execution status is set to false for 1 line).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>16-bit Not Equal To</code><br />
            <code>DXXXXXXX 0010YYYY</code>
        </td>
        <td>Checks if <code>YYYY</code> != (halfword at <code>[XXXXXXX]</code>).<br />If not, the following line is not executed (ie. execution status is set to false for 1 line).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>16-bit Less Than</code><br />
            <code>DXXXXXXX 0020YYYY</code>
        </td>
        <td>Checks if <code>YYYY</code> < (halfword at <code>[XXXXXXX]</code>).<br />If not, the following line is not executed (ie. execution status is set to false for 1 line).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>16-bit Greater Than</code><br />
            <code>DXXXXXXX 0030YYYY</code>
        </td>
        <td>Checks if <code>YYYY</code> > (halfword at <code>[XXXXXXX]</code>).<br />If not, the following line is not executed (ie. execution status is set to false for 1 line).</td>
    </tr>
    <tr><th colspan="2">Multiple Skip Conditional Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0x0E</code><br />
            <code>8-bit Equal To</code><br />
            <code>E1ZZYYYY 0XXXXXXX</code>
        </td>
        <td>Checks if <code>YY</code> == (byte at <code>[XXXXXXX]</code>).<br />If not, the next <code>ZZ</code> are not executed (ie. execution status is set to false for <code>ZZ</code> lines).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0E</code><br />
            <code>8-bit Not Equal To</code><br />
            <code>E1ZZYYYY 1XXXXXXX</code>
        </td>
        <td>Checks if <code>YY</code> != (byte at <code>[XXXXXXX]</code>).<br />If not, the next <code>ZZ</code> are not executed (ie. execution status is set to false for <code>ZZ</code> lines).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0E</code><br />
            <code>8-bit Less Than</code><br />
            <code>E1ZZYYYY 2XXXXXXX</code>
        </td>
        <td>Checks if <code>YY</code> < (byte at <code>[XXXXXXX]</code>).<br />If not, the next <code>ZZ</code> are not executed (ie. execution status is set to false for <code>ZZ</code> lines).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0E</code><br />
            <code>8-bit Greater Than</code><br />
            <code>E1ZZYYYY 3XXXXXXX</code>
        </td>
        <td>Checks if <code>YY</code> > (byte at <code>[XXXXXXX]</code>).<br />If not, the next <code>ZZ</code> are not executed (ie. execution status is set to false for <code>ZZ</code> lines).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0E</code><br />
            <code>16-bit Equal To</code><br />
            <code>EZZZYYYY 0XXXXXXX</code>
        </td>
        <td>Checks if <code>YYYY</code> == (halfword at <code>[XXXXXXX]</code>).<br />If not, the next <code>ZZZ</code> are not executed (ie. execution status is set to false for <code>ZZZ</code> lines).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0E</code><br />
            <code>16-bit Not Equal To</code><br />
            <code>EZZZYYYY 1XXXXXXX</code>
        </td>
        <td>Checks if <code>YYYY</code> != (halfword at <code>[XXXXXXX]</code>).<br />If not, the next <code>ZZZ</code> are not executed (ie. execution status is set to false for <code>ZZZ</code> lines).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0E</code><br />
            <code>16-bit Less Than</code><br />
            <code>EZZZYYYY 2XXXXXXX</code>
        </td>
        <td>Checks if <code>YYYY</code> < (halfword at <code>[XXXXXXX]</code>).<br />If not, the next <code>ZZZ</code> are not executed (ie. execution status is set to false for <code>ZZZ</code> lines).</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0E</code><br />
            <code>16-bit Greater Than</code><br />
            <code>EZZZYYYY 3XXXXXXX</code>
        </td>
        <td>Checks if <code>YYYY</code> > (halfword at <code>[XXXXXXX]</code>).<br />If not, the next <code>ZZZ</code> are not executed (ie. execution status is set to false for <code>ZZZ</code> lines).</td>
    </tr>
    <tr><th colspan="2">Address Conditional Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>Address Equal To</code><br />
            <code>DXXXXXXX 4YYYYYYY</code><br />
            <code>ZZZZZZZZ 0000000W</code>
        </td>
        <td>Checks if value at <code>[XXXXXXX]</code> == value at <code>[YYYYYYY]</code>.<br />If not, the next <code>ZZZZZZZZ</code> lines are not executed (ie. execution status is set to false for <code>ZZZ</code> lines).<br /><code>W</code> = Address type; 0 - 8-bit, 1 - 16-bit, 2 - 32-bit</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>Address Not Equal To</code><br />
            <code>DXXXXXXX 5YYYYYYY</code><br />
            <code>ZZZZZZZZ 0000000W</code>
        </td>
        <td>Checks if value at <code>[XXXXXXX]</code> != value at <code>[YYYYYYY]</code>.<br />If not, the next <code>ZZZZZZZZ</code> lines are not executed (ie. execution status is set to false for <code>ZZZ</code> lines).<br /><code>W</code> = Address type; 0 - 8-bit, 1 - 16-bit, 2 - 32-bit</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>Address Less Than</code><br />
            <code>DXXXXXXX 6YYYYYYY</code><br />
            <code>ZZZZZZZZ 0000000W</code>
        </td>
        <td>Checks if value at <code>[XXXXXXX]</code> < value at <code>[YYYYYYY]</code>.<br />If not, the next <code>ZZZZZZZZ</code> lines are not executed (ie. execution status is set to false for <code>ZZZ</code> lines).<br /><code>W</code> = Address type; 0 - 8-bit, 1 - 16-bit, 2 - 32-bit</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>Address Greater Than</code><br />
            <code>DXXXXXXX 7YYYYYYY</code><br />
            <code>ZZZZZZZZ 0000000W</code>
        </td>
        <td>Checks if value at <code>[XXXXXXX]</code> > value at <code>[YYYYYYY]</code>.<br />If not, the next <code>ZZZZZZZZ</code> lines are not executed (ie. execution status is set to false for <code>ZZZ</code> lines).<br /><code>W</code> = Address type; 0 - 8-bit, 1 - 16-bit, 2 - 32-bit</td>
    </tr>
    <tr><th colspan="2">Boolean Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0x07</code><br />
            <code>8-bit OR</code><br />
            <code>7XXXXXXX 000000YY</code>
        </td>
        <td>Writes byte (byte at <code>[XXXXXXX]</code> OR <code>YY</code>) to <code>[XXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x07</code><br />
            <code>8-bit AND</code><br />
            <code>7XXXXXXX 000200YY</code>
        </td>
        <td>Writes byte (byte at <code>[XXXXXXX]</code> AND <code>YY</code>) to <code>[XXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x07</code><br />
            <code>8-bit XOR</code><br />
            <code>7XXXXXXX 000400YY</code>
        </td>
        <td>Writes byte (byte at <code>[XXXXXXX]</code> XOR <code>YY</code>) to <code>[XXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x07</code><br />
            <code>16-bit OR</code><br />
            <code>7XXXXXXX 000100YY</code>
        </td>
        <td>Writes halfword (halfword at <code>[XXXXXXX]</code> OR <code>YYYY</code>) to <code>[XXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x07</code><br />
            <code>16-bit AND</code><br />
            <code>7XXXXXXX 000300YY</code>
        </td>
        <td>Writes halfword (halfword at <code>[XXXXXXX]</code> AND <code>YYYY</code>) to <code>[XXXXXXX]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x07</code><br />
            <code>16-bit XOR</code><br />
            <code>7XXXXXXX 000500YY</code>
        </td>
        <td>Writes halfword (halfword at <code>[XXXXXXX]</code> XOR <code>YYYY</code>) to <code>[XXXXXXX]</code>.</td>
    </tr>
    <tr><th colspan="2">Pointer Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0x06</code><br />
            <code>8-bit</code><br />
            <code>...</code>
        </td>
        <td>TODO... well the TODO has been here since at least 2011... I don't know if I'm ever going to do it at this point.</td>
    </tr>
    <tr><th colspan="2">Miscellaneous Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>Button Press</code><br />
            <code>D00000YY 1XXXXXXX</code>
        </td>
        <td>Checks if <code>ctrl & XXXXXXX</code> == <code>XXXXXXX</code>.<br />If not, the next <code>YY+1</code> lines are not executed (ie. execution status is set to false for <code>YY+1</code> lines). See <a href="../other/button-activators.md">button activators</a> for possible values.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0D</code><br />
            <code>Inverse Button Press</code><br />
            <code>D00000YY 3XXXXXXX</code>
        </td>
        <td>Checks if <code>ctrl & XXXXXXX</code> != <code>XXXXXXX</code>.<br />If not, the next <code>YY+1</code> lines are not executed (ie. execution status is set to false for <code>YY+1</code> lines). See <a href="../other/button-activators.md">button activators</a> for possible values.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x05</code><br />
            <code>Copy Bytes</code><br />
            <code>5XXXXXXX ZZZZZZZZ</code><br />
            <code>0YYYYYYY 0000000</code>
        </td>
        <td>Copies <code>ZZZZZZZZ</code> bytes from <code>[XXXXXXX]</code> to <code>[YYYYYYY]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x04</code><br />
            <code>32-bit Multi Write</code><br />
            <code>4XXXXXXX YYYYZZZZ</code><br />
            <code>VVVVVVVV WWWWWWWW</code>
        </td>
        <td>Starting at address <code>[XXXXXXX]</code>, this code will loop <code>YYYY</code> times.<br />The next address is determined by the incrementing the current address by (ZZZZ * 4).<br />The value written to the address is specified by <code>VVVVVVVV+(WWWWWWWW * loop count)</code>.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0B</code><br />
            <code>Pause</code><br />
            <code>B0000000 XXXXXXXX</code>
        </td>
        <td>Delays the code engine for <code>XXXXXXXX</code> cycles. Will delay the application of all following code lines.<br />Simply performs <code>sceKernelDelayThread(XXXXXXXX)</code>, hopefully this is what CWCheat does when this code type is encountered.</td>
    </tr>
    <tr>
        <td>
            <code>Type 0x0C</code><br />
            <code>32-bit Equal To</code><br />
            <code>CXXXXXXX YYYYYYYY</code>
        </td>
        <td>Checks if <code>YYYYYYYY</code> == (word at <code>[XXXXXXX]</code>).<br />If not, the remainder of the code is not executed (ie. execution status is set to false until the next cheat is reached).</td>
    </tr>
</table>
