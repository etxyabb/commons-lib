# What?

The WizTools.org Commons Library (part of [WizTools.org](http://www.wiztools.org/) project) is a rich collection of commonly used convenience classes and data-structures for Java.

This is developed and maintained by [Subhash Chandran](https://www.ohloh.net/accounts/subwiz).

## Dependency

    <dependency>
        <groupId>org.wiztools.commons</groupId>
        <artifactId>wiztools-commons-lib</artifactId>
        <version>0.3.0</version>
    </dependency>

This library does not depend on any external libraries.

## Examples

**Note**: The examples are for bringing to your attention the features of this library. It is a small sample of the rich content in this library.

All classes are from the package:

    import org.wiztools.commons.*;

### Content of File

	File f = ...;
	FileUtil.getContentAsString(f, Charsets.UTF_8);

[FileUtil.java](https://bitbucket.org/wiztools/wiztools-commons-lib/src/tip/src/main/java/org/wiztools/commons/FileUtil.java)

### Non-RE based split()

	String splitStr = ...;
	String input = ...;
	List<String> arr = StringUtil.explode(splitStr, input);

[StringUtil.java](https://bitbucket.org/wiztools/wiztools-commons-lib/src/tip/src/main/java/org/wiztools/commons/StringUtil.java)

### Encode XML/HTML special characters

	String encoded = XmlEntityEncode.encode(input);

[XmlEntityEncode.java](https://bitbucket.org/wiztools/wiztools-commons-lib/src/tip/src/main/java/org/wiztools/commons/XmlEntityEncode.java)

### Java equivalent of PHP md5() function

	String input = ...;
	String hash = DigestUtil.md5hex(input.getBytes("UTF-8"));

[DigestUtil.java](https://bitbucket.org/wiztools/wiztools-commons-lib/src/tip/src/main/java/org/wiztools/commons/DigestUtil.java)

### Map data-structure holding multiple values

	MultiValueMap<String, String> m = new MultiValueMapArrayList<String, String>();

	m.put("key1", "value1");
	m.put("key1", "value2");

	// Returns "value1" and "value2":
	Collection<String, String> values =  m.get("key1");

[MultiValueMap.java](https://bitbucket.org/wiztools/wiztools-commons-lib/src/tip/src/main/java/org/wiztools/commons/MultiValueMap.java) [MultiValueMapArrayList.java](https://bitbucket.org/wiztools/wiztools-commons-lib/src/tip/src/main/java/org/wiztools/commons/MultiValueMapArrayList.java)

### Service Locator To Load Implementation

    // The relationship between MyInterface and MyInterfaceImplClass
    // needs to be defined in the properties file
    // wiztools-service-locator.properties and should be available in
    // the classpath. The association is defined thus:
    // com.package.MyInterface = com.package.MyInterfaceImplClass

    MyInterface obj = Implementation.of(MyInterface.class);

[Implementation.java](https://bitbucket.org/wiztools/wiztools-commons-lib/src/tip/src/main/java/org/wiztools/commons/Implementation.java)