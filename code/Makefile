BIN := ./bin
INCLUDE := ./include
OBJ := ./obj
SRC := ./src
APPS := ./app

CC := gcc
FLAGS := -o2 -Wall
RM := rm -rf


# Compile my libs, compile my apps
# all: mylibs myapps

# Compile our libs
# mylibs: \
#	$(OBJ)/

# Compile our apps
# myapps: \
#	$(BIN)/

# Generic flag to any object file
# obj.o (object) depends on obj.c file and obj.h
$(OBJ)/%.o: $(SRC)/%.c $(INCLUDE)/%.h
	$(CC) $(FLAGS) -c $< -I $(INCLUDE) -o $@

# Generic flag to any bin file
# app (bin) depends on app.c file and all obj.h files
$(BIN)/%: $(APPS)/%.c $(OBJ)/*.o
	$(CC) $(FLAGS) $< $(OBJ)/*.o -I $(INCLUDE) -o $@

# Run main app
run:
	./$(BIN)/app

# Clean all bin and object files
clean:
	@echo "Removing all object files and bin files"
	$(RM) $(OBJ)/*.o $(BIN)/*