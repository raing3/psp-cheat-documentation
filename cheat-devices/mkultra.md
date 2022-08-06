## MKUltra

### Description

MKUltra by RedHate is a mod of NitePR which features a number of changes including register highlighting for the
disassembler, POPS support, improved copier, configurable colours, support for more MIPS opcodes and an additional
code type.

### Code types

Supports the same code types as [NitePR](nitepr.md) in addition to the below.

<table>
    <tr>
        <th>Type</th>
        <th>Description</th>
    </tr>
    <tr><th colspan="2">Button Press Code Types</th></tr>
    <tr>
        <td>
            <code>Type 0xFF</code><br />
            <code>Button Press</code><br />
            <code>FFYYYYYY 0XXXXXXX</code>
        </td>
        <td>Checks if <code>YYYYYY</code> == <code>(value at [XXXXXXX]) & YYYYYY</code>.<br />If not, the code(s) following this one are not executed.</td>
    </tr>
</table>
