# Frequently Asked Questions about Sample Board Solutions for Libero
Some of the more frequently asked questions are covered here. If you have a question that haven't been answered you can always contact the support by raising a ticket through the ticket systetm on GitHub.

## F.A.Q's

**Q:** Can I modify the frequency of the design?

**A:** Yes. The design's frequency can be modified to suit the needs of the user, although when the frequency of the design is modified it's necessary to ensure there are no timing violations. Each time the frequency is changed, the canvas needs to be re-generated, hierarchy needs to be re-built, constraints need to be re-derived and finally before bitstream is generated the "Verify Timing" option in the design flow has to be ran and produce a green tick beside it signifying no timing violations due to new frequency. If the changed frequency causes violations, then changes need to be made to the design/constraints otherwise design is not guaranteed to work.

##

**Q:** Can I run scripts with arguments when project is already built?

**A:** Yes, you can still pass arguments to build the project to certain stages in the design flow when the project is already built.
   If the project is already built, it has to be open to run arguments. 
##

**Q:** What files are contained within the import folder to the .tcl script that is executed?

**A:** The files within that folder are files that could not otherwise be included in the script and are needed for the project to be built.
   Some of the files in the folder include:
	- Lower level tcl scripts that focus on importing constraints and building the canvas
	- Timing constraints and pin assignments.
	- HDL components that are imported into the design.
##
	
**Q:** Do the designs include all of the features made available by the board used?

**A:** No, these are sample board design projects and are basic in nature. They serve the purpose of getting the
   user started on building their own design and leaving them to implement whichever features they require. Links to Microsemi's websites have been provided. Where users can learn all of the features and limitations of each board solution and then modify their designs.
##

**Q:** Is 50MHz the maximum frequency on which the sample project is capapble of running on?

**A:** No, all of the designs have an operating frequency of 50MHz to make the use of SoftConsole project easier and to have a standard
   all sample designs can adhere to. The user has the freedom to change the frequency of the design to whatever suits them as long
   as it is within the designs specification.
##
   

**Q:** I typed in one of the four Design Flow Arguments yet my project hasn't built to that stage and gave me an error. What is wrong?

**A:** This is most likely due to the **first** argument not being entered. The four design flow arguments are **secondary**
arguments and therefore they always need to be entered after the first: "AXI" or "AHB" argument. If the first field
is left blank and only the secondary argument is entered the software will recognize it as a first argument which will
give the user an error. Always enter the first *target* argument before the second argument.
##

**Q:** Where are the STP and the PPD programming files? 

**A:** The .job programming file now contains both the PPD and the STP programming files and it can be used to program your target device using the FlashPro Express. Link to which
is provided on the design's page.
##

**Q:** I'm using FlashPro and it doesn't recognize the .job programming file. Why is that?

**A:** FlashPro does not support the .job programming file. It can only be programmed using the **FlashPro Express** a.k.a FPExpress. You may need to download FPExpress from the links
found on the design's page if it's not already found on your drive.
##

**Q:** My Libero has crashed or turned off while I was executing a script. What should I do?

**A:** If Libero crashes while executing the script then go into the script's folder and delete the project folder that was partially built. Then re-run the script again. Deleting the previously partially built folder ensures the next build will be clean.

**Q:** I got an error while executing a script on Synthesis that refers to the SRAM_0 or PF_SRAM_ component being not found. What should I do?
	
**A:**  Check if your file path is long enough for the project. This particular component uses long paths to be unpacked onto the design. If file path is sufficient then, exit Libero, delete the created project folder, run the script again.

