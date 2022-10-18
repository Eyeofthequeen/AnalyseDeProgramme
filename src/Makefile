SOURCEDIR := .
OBJECTSDIR := obj
OUTPUTDIR := out

SOURCES := $(shell find $(SOURCEDIR) -type f -name "*.jj")

#OUTPUTFILES := $(subst jj,java, $(SOURCES))
#SUBFOLDER := $(addprefix $(OUTPUTDIR)/, $(addsuffix /,$(basename $(notdir $(SOURCES)))))
#OUTPUT := $(join $(SUBFOLDER),$(notdir $(OUTPUTFILES)))

#SOURCES := StatsAttributs.jj
#SOURCES := Test.jj

.PHONY: all clean $(SOURCES)

all: $(SOURCES)
	@mkdir -p $(OBJECTSDIR)
	@mkdir -p $(OUTPUTDIR)

$(SOURCES):
	@echo
	@echo Removing old files from $@...
	-rm -r $(OBJECTSDIR)/$(basename $@)/*
	-rm -r $(OUTPUTDIR)/$(basename $@)/*
	@echo Parsing $@...
	javacc -output_directory:$(OBJECTSDIR)/$(basename $@) $@
	@echo Compilling $@...
	javac -d $(OUTPUTDIR)/$(basename $@) $(OBJECTSDIR)/$(basename $@)/*.java
	@echo Adding test file to directory...
	-cp $(SOURCEDIR)/testfile $(OUTPUTDIR)/$(basename $@)/testfile

clean:
	-@rm -r $(OBJECTSDIR)
	-@rm -r $(OUTPUTDIR)
