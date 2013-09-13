SCHEMATIC = arduino_can_interface.sch

all: check

check: 
	~/geda/bin/gnetlist -g drc2 $(SCHEMATIC) -o drc_output.txt
	cat drc_output.txt

gsch2pcb:
	~/geda/bin/gsch2pcb project

pcb:
	~/geda/bin/pcb board.pcb&

schematic:
	~/geda/bin/gschem $(SCHEMATIC)&

bom:
	~/geda/bin/gnetlist -g bom -o bom.txt $(SCHEMATIC)
#	gnetlist -g bom2 -o bom.txt $(SCHEMATIC)
#	gnetlist -g partslist1 -o bom.txt $(SCHEMATIC)
#	gnetlist -g partslist2 -o bom.txt $(SCHEMATIC)
#	gnetlist -g partslist3 -o bom.txt $(SCHEMATIC)
	cat bom.txt
#	gattrib -i $(SCHEMATIC)&

renum:
	refdes_renum $(SCHEMATIC)
#	~/geda/bin/refdes_renum --force $(SCHEMATIC)
.SILENT: check
