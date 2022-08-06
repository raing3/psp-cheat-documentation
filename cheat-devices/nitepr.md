## NitePR

### Description

NitePR by SANiK is widely known for its online cheating capabilities and open source license. NitePR supports a
very limited set of code types.

### Code types

<table>
    <tr>
        <th>Type</th>
        <th>Description</th>
    </tr>
    <tr><th colspan="2">Constant RAM Writes</th></tr>
    <tr>
        <td>
            <code>32-bit</code><br />
            <code>0XXXXXXX YYYYYYYY</code>
        </td>
        <td>Writes word <code>YYYYYYYY</code> to <code>[XXXXXXX+offset]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>16-bit</code><br />
            <code>0XXXXXXX YYYY</code>
        </td>
        <td>Writes halfword <code>YYYY</code> to <code>[XXXXXXX+offset]</code>.</td>
    </tr>
    <tr>
        <td>
            <code>8-bit</code><br />
            <code>0XXXXXXX YY</code>
        </td>
        <td>Writes byte <code>YY</code> to <code>[XXXXXXX+offset]</code>.</td>
    </tr>
    <tr><th colspan="2">Pointer Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0xFFFFFFFF</code><br />
            <code>Load Offset</code><br />
            <code>FFFFFFFF 0XXXXXXX</code>
        </td>
        <td>Loads the 32-bit value into the <code>offset</code>.<br /><code>offset</code> = word at <code>[XXXXXXX]</code>.</td>
    </tr>
</table>
