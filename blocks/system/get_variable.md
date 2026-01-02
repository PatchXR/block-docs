# Get Variable

**Category**: ⚙️ System

![get_variable thumbnail](https://portal.patchxr.io/block-thumbnails/get_variable.png)

## Description

Given a block and a variable name, if the block has the variable:
will output the value on the big output,
if the block doesn't have the variable:
will output 0 on the small output.

## Inputs, Outputs and Parts

**Input**: Blocks we want to read a variable from.

**Restrict (Optional)**: Restricts to a group: necessary if "set variable" uses it.

**Manual Trigger**: If connected: Trigger the block
If not connected: block trigger automatically when Input is changed

**Output**: Value of the variable on the block, if block has the value.

**Fail**: Send zero when connected block don't have the variable attached.

---