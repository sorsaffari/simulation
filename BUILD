java_library(
    name = "simulation",
    srcs = glob(["*.java"]),
    data = glob([
        "schema/*.gql",
        "data/*.yaml",
    ]),
    resources = [
        "conf/logback.xml",
    ],
    resource_strip_prefix = "conf/",
    deps = [
        "@graknlabs_client_java//:client-java",
        "@graknlabs_graql//java:graql",
        "//common:common",
        "//yaml_tool:yaml_tool",
        "//agents:agents",
    ],
)

java_binary(
    name = "simulation-binary",
    main_class = "grakn.simulation.Simulation",
    runtime_deps = [":simulation"],
)

java_binary(
    name = "simulation-binary-debug",
    main_class = "grakn.simulation.Simulation",
    runtime_deps = [":simulation"],
    jvm_flags = [
        "-Xdebug",
        "-Xrunjdwp:transport=dt_socket,server=y,address=5005",
    ]
)