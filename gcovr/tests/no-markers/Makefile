all:
	$(CXX) -fprofile-arcs -ftest-coverage -fPIC main.cpp -o testcase

run: txt xml html sonarqube json

MARKER_OPT ?= --no-markers

txt:
	./testcase
	$(GCOVR) -d $(MARKER_OPT) -o coverage.txt

xml:
	./testcase
	$(GCOVR) -d $(MARKER_OPT) -x -o coverage.xml

html:
	./testcase
	$(GCOVR) -d $(MARKER_OPT) --html-details -o coverage.html

sonarqube:
	./testcase
	$(GCOVR) -d $(MARKER_OPT) --sonarqube sonarqube.xml

json:
	./testcase
	$(GCOVR) -d $(MARKER_OPT) --json-pretty -o coverage.json

clean:
	rm -f testcase
	rm -f *.gc*
	rm -f coverage.txt coverage.xml coverage*.html sonarqube.xml coverage.json
