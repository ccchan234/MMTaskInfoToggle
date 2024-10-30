history:

i wanna make a macro to toggle task info view/hide in mm2020. tell me what to check. dont code yet.

(webpage discussion)

I understand you want to create a macro to toggle task information visibility in MindManager 2020. Before writing the code, here's what we need to consider:

1. **Key Components**:
- We'll need to use the `Document.Filter.SetViewFilter()` method
- The flag we'll use is `mmViewFilterFlags.mmViewFilterFlagHideTaskInformation`
- We'll need to track the current state (visible/hidden) to toggle properly

2. **Implementation Approach**:
- Create a simple macro that checks current state
- Toggle between showing and hiding task information
- Can be assigned to a button in the ribbon or quick access toolbar

3. **Requirements**:
- MindManager 2020 (compatible since MM5)
- Basic VBScript knowledge
- Access to macro editor in MindManager

Would you like me to proceed with the macro code implementation?

can you verify with this official api? dont code yet.

Looking at the official API documentation you've shared, I can verify that:
The Filter property is indeed part of the Document object
It's been available since Object Model Version 5.0.1 (which means it will work in MM2020)
It's a read-only property that returns a Filter object
However, I notice that the specific method SetViewFilter() and the flag mmViewFilterFlagHideTaskInformation aren't directly shown in this particular documentation page. To proceed safely, we should:
Verify the existence of SetViewFilter() method in the Filter object documentation
Confirm the mmViewFilterFlags enumeration values
Could you share the API documentation for:
The Filter object methods
The ViewFilter flags enumeration
This will help ensure we're using the correct method and flags before implementing the macro.

Perfect! Now I can verify everything from the official documentation:
1. Filter Methods Confirmed:
GetViewFilter and SetViewFilter are officially documented methods
They work with the MmViewFilterFlags enumeration
Task Information Flag Confirmed:
mmViewFilterFlagHideTaskInformation exists with value 128
It's specifically designed for hiding task information
Example Code Provided:
The documentation even includes a sample macro that demonstrates exactly what you want to do
It shows the proper way to toggle task information visibility using bitwise operations
Important Notes:
The API has been consistent since early versions
The method works with the active document
It uses proper bitwise operations to toggle the flag without affecting other view settings
Everything checks out perfectly with the official API documentation. Would you like me to proceed with creating the macro code now?

Based on the official documentation, here's the WinWrap Basic macro to toggle task information visibility:
To use this macro:
Open the Macro Editor in MindManager 2020
Create a new macro and paste this code
Save it with a name like "ToggleTaskInfo"
4. You can then assign it to a button in the Quick Access Toolbar or ribbon for easy access
The macro:
Gets the current view filter state
Uses bitwise operations to check if task info is currently hidden
Toggles the state while preserving other view filter settings
Works on the currently active document
Would you like instructions on how to add this to your Quick Access Toolbar?
