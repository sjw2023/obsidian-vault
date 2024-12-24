# Set JAVA_HOME to Java 11
$env:JAVA_HOME = "C:\Program Files\Java\jdk-11.0.9"

# Update PATH to include the bin directory of the selected Java version
$env:PATH = "$env:JAVA_HOME\bin;$env:PATH"

# Verify the Java version
java -version