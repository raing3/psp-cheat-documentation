## Button activators

### Description

The PSP offers various `sceCtrl*` functions for reading the state of the buttons. These functions provide the button
state as a single integer bit mask.

Depending on the cheat device being used the following options may be available for reading the button state:

 * Use a code type (or similar) specifically provided by the cheat device to read button state.
 * Identify the memory address where the game writes button state to and use the condition types or assembly to
   toggle the cheat.

### Button bit flags

The following table shows the possible values of the controller button data. Note that the kernel mode flags will
**NOT** be available when using button data that has been read by the game. 

<table>
    <tr>
        <th>Button</th>
        <th>Code</th>
    </tr>
    <tr>
        <th colspan="2">User mode flags</th>
    </tr>
    <tr>
        <td>PSP_CTRL_SELECT</td>
        <td>0x00000001</td>
    </tr>
    <tr>
        <td>PSP_CTRL_START</td>
        <td>0x00000008</td>
    </tr>
    <tr>
        <td>PSP_CTRL_UP</td>
        <td>0x00000010</td>
    </tr>
    <tr>
        <td>PSP_CTRL_RIGHT</td>
        <td>0x00000020</td>
    </tr>
    <tr>
        <td>PSP_CTRL_DOWN</td>
        <td>0x00000040</td>
    </tr>
    <tr>
        <td>PSP_CTRL_LEFT</td>
        <td>0x00000080</td>
    </tr>
    <tr>
        <td>PSP_CTRL_LTRIGGER</td>
        <td>0x00000100</td>
    </tr>
    <tr>
        <td>PSP_CTRL_RTRIGGER</td>
        <td>0x00000200</td>
    </tr>
    <tr>
        <td>PSP_CTRL_TRIANGLE</td>
        <td>0x00001000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_CIRCLE</td>
        <td>0x00002000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_CROSS</td>
        <td>0x00004000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_SQUARE</td>
        <td>0x00008000</td>
    </tr>
    <tr>
        <th colspan="2">Kernel mode flags</th>
    </tr>
    <tr>
        <td>PSP_CTRL_HOME</td>
        <td>0x00010000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_HOLD</td>
        <td>0x00020000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_NOTE</td>
        <td>0x00800000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_SCREEN</td>
        <td>0x00400000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_VOLUP</td>
        <td>0x00100000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_VOLDOWN</td>
        <td>0x00200000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_WLAN_UP</td>
        <td>0x00040000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_REMOTE</td>
        <td>0x00080000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_DISC</td>
        <td>0x01000000</td>
    </tr>
    <tr>
        <td>PSP_CTRL_MS</td>
        <td>0x02000000</td>
    </tr>
</table>