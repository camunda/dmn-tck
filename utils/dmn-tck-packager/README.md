# DMN TCK Packager

This utility can package/extract DMN TCK Test Cases file in DMN XML file extended attributes.

The TCK test cases are packaged in the DMN model `definitions` level as an `extensionElements`.

```
<semantic:definitions xmlns:semantic="https://www.omg.org/spec/DMN/20230324/MODEL/" xmlns:tc="http://www.omg.org/spec/DMN/20160719/testcase">
    <semantic:extensionElements>
        <tc:testCases>
            <tc:testCase id="tc-1" name="Test Case 1">
				...
			</tc:testCase>
            <tc:testCase id="tc-2" name="Test Case 2">
				...
			</tc:testCase>
		</tc:testCases>
</semantic>
```


## Building the Packager

```
$ mvn clean install
```

This will generate an executable jar file located in the target folder with the name dmn-tck-packager-[version].one-jar.

You can then use this executable jar to package/extract your DMN TCK Tests
```
$ java -jar dmn-tck-packager-[version].one-jar
```

#### Extract Test Cases from DMN XML

To extract DMN TCK Tests from dmn-source.xml and write them in tck-destination.xml:

```
$ java -jar dmn-tck-packager-[version].one-jar -x dmn-source.xml tck-destination.xml [dmn-destination.xml]
```

You optionally add an extra parameter (dmn-destination.xml) that will contain the dmn file without the test case extension

#### Package Test Cases in DMN XML

To package the DMN TCK file tck-source.xml  in the DMN XML file dmn-source.xml and write the result to the DMN XML file dmn-destination.xml:

```
java -jar dmn-tck-packager.jar -c dmn-source.xml tck-source.xml dmn-destination.xml
```
