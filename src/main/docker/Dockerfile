FROM ${docker.pull.registry}/platformx/java/jre-headless:${docker.jre.version}

ADD entrypoint.sh entrypoint.sh

ADD maven/${project.build.finalName}.jar ${project.build.finalName}.jar

ENTRYPOINT ["sh","./entrypoint.sh"]
