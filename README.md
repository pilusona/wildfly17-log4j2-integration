# wildfly-log4j2
This sample source code will help you to configure the log4j2 into WildFly 17.0.1.

Configure the  standalone.xml logging subsystem as follows:

	<subsystem xmlns="urn:jboss:domain:logging:7.0">
		<custom-handler name="FILE" class="com.schema.infra.util.logger.handlers.WildFly2Log4j2LogDelegator" module="com.schema.infra.util.logger.handlers"/>
		<logger category="com.arjuna">
			<level name="WARN"/>
		</logger>
		<logger category="org.apache.tomcat.util.modeler">
			<level name="WARN"/>
		</logger>
		<logger category="org.apache.ftpserver">
			<level name="WARN"/>
		</logger>
		<logger category="io.jaegertracing.Configuration">
			<level name="WARN"/>
		</logger>
		<logger category="org.jboss.as.config">
			<level name="DEBUG"/>
		</logger>
		<logger category="sun.rmi">
			<level name="WARN"/>
		</logger>
		<logger category="jacorb">
			<level name="WARN"/>
		</logger>
		<logger category="jacorb.config">
			<level name="ERROR"/>
		</logger>
		<logger category="org.hibernate">
			<level name="INFO"/>
		</logger>
		<logger category="org.hibernate.type">
			<level name="INFO"/>
		</logger>
		<logger category="org.hibernate.tool.hbm2ddl">
			<level name="INFO"/>
		</logger>
		<logger category="org.hibernate.SQL">
			<level name="INFO"/>
		</logger>
		<logger category="org.jboss.jca">
			<level name="INFO"/>
		</logger>
		<logger category="org.springframework">
			<level name="INFO"/>
		</logger>
		<logger category="org.apache.commons.digester.Digester">
			<level name="INFO"/>
		</logger>
		<logger category="org.jboss.ejb.client">
			<level name="INFO"/>
		</logger>
		<logger category="org.apache.http">
			<level name="INFO"/>
		</logger>
		<logger category="org.jboss.security">
			<level name="INFO"/>
		</logger>
		<logger category="org.jboss.resteasy">
			<level name="INFO"/>
		</logger>
		<logger category="org.quartz">
			<level name="INFO"/>
		</logger>
		<root-logger>
			<level name="INFO"/>
			<handlers>
				<handler name="FILE"/>
			</handlers>
		</root-logger>
		<formatter name="PATTERN">
			<pattern-formatter pattern="%d{yyyy-MM-dd HH:mm:ss,SSS} %-5p [%c] (%t) %s%E%n"/>
		</formatter>
		<formatter name="COLOR-PATTERN">
			<pattern-formatter pattern="%K{level}%d{HH:mm:ss,SSS} %-5p [%c] (%t) %s%e%n"/>
		</formatter>
	</subsystem>