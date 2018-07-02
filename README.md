# Zabbix-lm-sensors-lld
Simple bash script which returns {#CHIP}, {#SENSOR} and {#UNITS} macros. That macros should be used with native **sensor** type zabbix-agent items. Script depends on lm-sensors to work.

Should work with older zabbix (but I haven't opportunity to test it). Basic template attached as an example.

Installation:

- Check that paths to **egrep**, **cut**, **tr** and sensors are valid.
- Run script as zabbix user, check that it returns valid output
- Drop **userparameter_sensors.conf** in **zabbix_agentd.conf.d** directory.

Example output:

    {
    	"data":[
    		{"{#CHIP}":"w83795adg-i2c-1-2f", "{#SENSOR}":"temp5", "{#UNITS}":"°C"},
    		{"{#CHIP}":"w83795adg-i2c-1-2f", "{#SENSOR}":"temp2", "{#UNITS}":"°C"},
    		{"{#CHIP}":"w83795adg-i2c-1-2f", "{#SENSOR}":"temp1", "{#UNITS}":"°C"},
    		{"{#CHIP}":"w83795adg-i2c-1-2f", "{#SENSOR}":"fan1", "{#UNITS}":"RPM"},
    		{"{#CHIP}":"w83795adg-i2c-1-2f", "{#SENSOR}":"in13", "{#UNITS}":"V"},
    		{"{#CHIP}":"w83795adg-i2c-1-2f", "{#SENSOR}":"in12", "{#UNITS}":"V"},
    		{"{#CHIP}":"w83795adg-i2c-1-2f", "{#SENSOR}":"in3", "{#UNITS}":"V"},
    		{"{#CHIP}":"w83795adg-i2c-1-2f", "{#SENSOR}":"in2", "{#UNITS}":"V"},
    		{"{#CHIP}":"w83795adg-i2c-1-2f", "{#SENSOR}":"in1", "{#UNITS}":"V"},
    		{"{#CHIP}":"w83795adg-i2c-1-2f", "{#SENSOR}":"in0", "{#UNITS}":"V"},
    		{"{#CHIP}":"jc42-i2c-0-19", "{#SENSOR}":"temp1", "{#UNITS}":"°C"},
    		{"{#CHIP}":"k10temp-pci-00c3", "{#SENSOR}":"temp1", "{#UNITS}":"°C"}
    	]
    }
