# REA breakdown: integromat/make-mcp-server / .

Tool: rea-agents@6.5.0 (morluto/rea, MIT), static analysis, 2026-11-07.

## Routes / pages found

## Settings / billing / api-key / usage files

## REA output (trimmed)
## evidence_id

ev_7822014ee780d303113960310a7ad6fbc4cf8ad2188c062833fe8fb86e369f03

## subject.name

target

## subject.digest

| Key    | Value                                                            |
|--------|------------------------------------------------------------------|
| sha256 | 932a43285f641cff707cc5af03cc7390b93965b2095d8aeb9b1aa769dacd868b |

## subject.local_path

/tmp/target

## subject.format

directory

## subject.architecture

null

## provider

| Key     | Value                               |
|---------|-------------------------------------|
| id      | rea-javascript-application          |
| name    | REA JavaScript application analyzer |
| version | 1                                   |

## analysis_profile

null

## predicate_type

rea.javascript-application-analysis

## operation

analyze_javascript_application

## parameters

| Key              | Value |
|------------------|-------|
| format           | auto  |
| integrity_policy | fail  |

## raw_result

null

## normalized_result.input_path

/tmp/target

## normalized_result.format

directory

## normalized_result.root_artifact_sha256

932a43285f641cff707cc5af03cc7390b93965b2095d8aeb9b1aa769dacd868b

## normalized_result.inventory_manifest_id

agm_4374ae7f1c892fb53cdef0059285f323d68a88bd8aa9660c538f44a3c6d582d8

## normalized_result.inventory_graph_sha256

c6e8b97ab8702fffdb2593909481707f207cb3b372b4b377c6eb469709891901

## normalized_result.integrity_contradictions



## normalized_result.graph.schema

JavaScriptApplicationGraph

## normalized_result.graph.root_node_ids

jag_node_ddf0858f5cac3c2264743ad2bd50d829768cf8bccccdc357cc8c70422f9ac9a6

## normalized_result.graph.nodes

| node_id                                                                   | kind              | identity        | observations    |
|---------------------------------------------------------------------------|-------------------|-----------------|-----------------|
| jag_node_06564f00a0f6579101111ac85b2569aad06268eacc706dbb320da340643b205f | javascript-module | [object Object] | [object Object] |
| jag_node_08c86458a4a20b1ba885990f77eb90758a8c44076d2afde4a3c02f6b097a37bf | artifact          | [object Object] | [object Object] |
| jag_node_9e74d750e2659992a5240dfa8aa6281ead39c502863d82cf2eaac9fb5a4d2669 | artifact          | [object Object] | [object Object] |
| jag_node_c21ec4685e0bff3f364c3dbb6434e56e661803f22d8f0418daf7df418f89fbba | artifact          | [object Object] | [object Object] |
| jag_node_c81a1323ffbfdf60b3f240be5877ba437e8d85a79e11b0c72d40588c037868b9 | javascript-asset  | [object Object] | [object Object] |
| jag_node_ca266a5f61072ef12317c24ff77d2f5a5ad43017a4dd3fb8af68e798ef1edc16 | artifact          | [object Object] | [object Object] |
| jag_node_d8f6b6e0162ff9a94d09f8fa4e33dafe5324626d89ec60c765611618967a1d76 | javascript-module | [object Object] | [object Object] |
| jag_node_dddc8b0511bc9010d83f9966514350d6441647d38b5ce45909b5aedce01c43ef | artifact          | [object Object] | [object Object] |
| jag_node_ddf0858f5cac3c2264743ad2bd50d829768cf8bccccdc357cc8c70422f9ac9a6 | package           | [object Object] | [object Object] |

## normalized_result.graph.edges

| source_node_id                                                            | target_node_id                                                            | relation | properties      | evidence        | edge_id                                                                   | identifier_strategy |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------|----------|-----------------|-----------------|---------------------------------------------------------------------------|---------------------|
| jag_node_c81a1323ffbfdf60b3f240be5877ba437e8d85a79e11b0c72d40588c037868b9 | jag_node_06564f00a0f6579101111ac85b2569aad06268eacc706dbb320da340643b205f | contains | [object Object] | [object Object] | jag_edge_05e3e4f6aaf9b87287428aee4ec4ea1b18314350a4f3f4d347fa4ea18e2bc52d | [object Object]     |
| jag_node_9e74d750e2659992a5240dfa8aa6281ead39c502863d82cf2eaac9fb5a4d2669 | jag_node_c21ec4685e0bff3f364c3dbb6434e56e661803f22d8f0418daf7df418f89fbba | contains | [object Object] | [object Object] | jag_edge_1d1891d205ba13fe27f6f658372ef9a2191bdcfc63aa0aed89c212936171f436 | [object Object]     |
| jag_node_ddf0858f5cac3c2264743ad2bd50d829768cf8bccccdc357cc8c70422f9ac9a6 | jag_node_9e74d750e2659992a5240dfa8aa6281ead39c502863d82cf2eaac9fb5a4d2669 | contains | [object Object] | [object Object] | jag_edge_1dfd6d2ef77fa8367b22de1b03a07aebdf1e33269f63808d2791d34d02f99358 | [object Object]     |
| jag_node_9e74d750e2659992a5240dfa8aa6281ead39c502863d82cf2eaac9fb5a4d2669 | jag_node_ca266a5f61072ef12317c24ff77d2f5a5ad43017a4dd3fb8af68e798ef1edc16 | contains | [object Object] | [object Object] | jag_edge_2ae5191a1288b87369f06f11103966fb37ef727023a39920b531bba0ebf7ca8f | [object Object]     |
| jag_node_9e74d750e2659992a5240dfa8aa6281ead39c502863d82cf2eaac9fb5a4d2669 | jag_node_dddc8b0511bc9010d83f9966514350d6441647d38b5ce45909b5aedce01c43ef | contains | [object Object] | [object Object] | jag_edge_8773f48fcdb5e7d3097abc06f05fb7aa5a60fb30a848c25b747b62212e41eb3e | [object Object]     |
| jag_node_9e74d750e2659992a5240dfa8aa6281ead39c502863d82cf2eaac9fb5a4d2669 | jag_node_08c86458a4a20b1ba885990f77eb90758a8c44076d2afde4a3c02f6b097a37bf | contains | [object Object] | [object Object] | jag_edge_94fdd8822126523352e25fc67f9f989fddbcc4d83402ab5c25df35db494f43a6 | [object Object]     |
| jag_node_06564f00a0f6579101111ac85b2569aad06268eacc706dbb320da340643b205f | jag_node_d8f6b6e0162ff9a94d09f8fa4e33dafe5324626d89ec60c765611618967a1d76 | exposes  | [object Object] | [object Object] | jag_edge_9b0e51ec94a3623234c8fe8ecc4b4071337bbef25c418b4909cd661cd23e3153 | [object Object]     |
| jag_node_9e74d750e2659992a5240dfa8aa6281ead39c502863d82cf2eaac9fb5a4d2669 | jag_node_c81a1323ffbfdf60b3f240be5877ba437e8d85a79e11b0c72d40588c037868b9 | contains | [object Object] | [object Object] | jag_edge_cd8be714fb227d624ad246e0682bfc58d4af27e95f733bf4e775133d185a768a | [object Object]     |

## normalized_result.graph.coverage.status

complete

## normalized_result.graph.coverage.truncated

false

## normalized_result.graph.coverage.omitted_count

0

## normalized_result.graph.coverage.limits



## normalized_result.graph.limitations

CommonJS and ESM binding relationships were recovered from inert syntax and resolved only within the inventoried artifact container.,JavaScript and HTML were parsed as inert text; bundle bootstrap code was never executed.,Static imports, entrypoints, workers, endpoints, and storage relationships do not prove runtime execution.,Static paths and relationships may remain unresolved when expressions are dynamic or obfuscated.,Webpack/Rspack factories were recovered from AST literals; REA did not invoke push handlers or bundle bootstrap code.

## normalized_result.graph.graph_id

jag_fcf6e6e8655b6659012267ef0f64c3ea759a5ec2beab7ccee1712d0a61a2cd91

## normalized_result.summary.browser_windows

0

## normalized_result.summary.explicit_web_preferences

0

## normalized_result.summary.preload_entrypoints

0

## normalized_result.summary.context_bridge_apis

0

## normalized_result.summary.exposed_api_members

0

## normalized_result.summary.ipc

| Key                                     | Value |
|-----------------------------------------|-------|
| operations                              | 0     |
| literal_channels                        | 0     |
| dynamic_channel_operations              | 0     |
| renderer_transmissions                  | 0     |
| renderer_listeners                      | 0     |
| main_handlers                           | 0     |
| paired_renderer_transmissions           | 0     |
| ambiguous_renderer_transmissions        | 0     |
| unpaired_literal_renderer_transmissions | 0     |

## normalized_result.summary.sender_validation_observations

0

## normalized_result.summary.utility_processes

0

## normalized_result.summary.resolved_utility_entrypoints

0

## normalized_result.summary.native_addon_bindings

0

## normalized_result.summary.resolved_native_addon_bindings

0

## normalized_result.statistics

| Key                     | Value  |
|-------------------------|--------|
| relevant_files          | 5      |
| nested_asar_containers  | 0      |
| text_bytes_read         | 215063 |
| invalid_utf8_files      | 0      |
| parsed_javascript_files | 1      |
| visited_ast_nodes       | 33     |
| findings                | 2      |
| modules                 | 0      |
| parse_failures          | 0      |

## normalized_result.limitations

CommonJS and ESM binding relationships were recovered from inert syntax and resolved only within the inventoried artifact container.,JavaScript and HTML were parsed as inert text; bundle bootstrap code was never executed.,Static imports, entrypoints, workers, endpoints, and storage relationships do not prove runtime execution.,Static paths and relationships may remain unresolved when expressions are dynamic or obfuscated.,Webpack/Rspack factories were recovered from AST literals; REA did not invoke push handlers or bundle bootstrap code.

## normalized_result.semantic_graph.schema

JavaScriptSemanticRelationGraph

## normalized_result.semantic_graph.root_artifact_sha256

932a43285f641cff707cc5af03cc7390b93965b2095d8aeb9b1aa769dacd868b

## normalized_result.semantic_graph.application_graph_id

jag_fcf6e6e8655b6659012267ef0f64c3ea759a5ec2beab7ccee1712d0a61a2cd91

## normalized_result.semantic_graph.root_node_ids

jsrg_node_743b84dceed7af9146f81913e2c47ec4e64a97a2250fc5949e6653b7a8bfee37

## normalized_result.semantic_graph.evidence_contexts

| authority                     | state    | confidence | artifact        | extractor       | coverage        | limitations                                                                                               | evidence_ids | context_id                                                                     |
|-------------------------------|----------|------------|-----------------|-----------------|-----------------|-----------------------------------------------------------------------------------------------------------|--------------|--------------------------------------------------------------------------------|
| ast-static-analysis           | observed | exact      | [object Object] | [object Object] | [object Object] |                                                                                                           |              | jsrg_evidence_55213da3f92e3a9489ec9f4bea642aa89974ea5d9ebb9c5663bcb2895351025a |
| static-relationship-inference | inferred | high       | [object Object] | [object Object] | [object Object] | This relationship is a conservative static candidate; it does not prove runtime execution or causal flow. |              | jsrg_evidence_95731ddff2ebfee4f243a5f565b1dac339f63e0b615c8b1b03fde6cdfaf44e08 |
| unknown                       | unknown  | unknown    | [object Object] | [object Object] | [object Object] | Binding Config has no constant initializer.                                                               |              | jsrg_evidence_a900134f40967365f49d90e63be79702aa1ca674891c4746f64d792ca4a05f1e |

## normalized_result.semantic_graph.nodes

| kind          | identity        | function_node_id | application_node_ids                                                      | label            | properties      | evidence        | node_id                                                                    |
|---------------|-----------------|------------------|---------------------------------------------------------------------------|------------------|-----------------|-----------------|----------------------------------------------------------------------------|
| property-slot | [object Object] |                  | jag_node_c81a1323ffbfdf60b3f240be5877ba437e8d85a79e11b0c72d40588c037868b9 | testEnvironment  | [object Object] | [object Object] | jsrg_node_00add50850f19a73a02d0afbd722c3489532af95fbef3c98dd1aaa2a3ed58426 |
| binding       | [object Object] |                  |                                                                           | Config           | [object Object] | [object Object] | jsrg_node_0ec5cfb8621f14b24572472716dbcf3e0de8af145bdec50acfeeb59a758c5e48 |
| literal       | [object Object] |                  |                                                                           | "node"           | [object Object] | [object Object] | jsrg_node_2370d5def5f808a6e543d712a5c600d05ddddf8eeb5eb8af31d4a509238b9ca1 |
| expression    | [object Object] |                  |                                                                           | Config           | [object Object] | [object Object] | jsrg_node_250cbf5497b6e01d609dde0ffda0ca581ef7c96125f0f24eae0dd5d0e25174c9 |
| literal       | [object Object] |                  |                                                                           | "$1"             | [object Object] | [object Object] | jsrg_node_29d6ee8e6d7d7b8d71cb4ba11e4556137fae42dbd7b846b770389e508e7aa3d2 |
| property-slot | [object Object] |                  | jag_node_c81a1323ffbfdf60b3f240be5877ba437e8d85a79e11b0c72d40588c037868b9 | ^(.*)\.js$       | [object Object] | [object Object] | jsrg_node_3042bbe69c4a1ed9864949393bdbfe53e7bbbb9e9ed6275be4f0c28e795a9a43 |
| property-slot | [object Object] |                  | jag_node_c81a1323ffbfdf60b3f240be5877ba437e8d85a79e11b0c72d40588c037868b9 | moduleNameMapper | [object Object] | [object Object] | jsrg_node_72ef8555edc820279c9dfcef32bf4b8929798fe0b77cd4222cb9a79cefc53de5 |
| module        | [object Object] |                  | jag_node_c81a1323ffbfdf60b3f240be5877ba437e8d85a79e11b0c72d40588c037868b9 | jest.config.ts   | [object Object] | [object Object] | jsrg_node_743b84dceed7af9146f81913e2c47ec4e64a97a2250fc5949e6653b7a8bfee37 |
| property-slot | [object Object] |                  | jag_node_c81a1323ffbfdf60b3f240be5877ba437e8d85a79e11b0c72d40588c037868b9 | 0                | [object Object] | [object Object] | jsrg_node_760faa59006483572177459ff91d447cd1bb8f69825f7067c65473f4f199c1e5 |
| property-slot | [object Object] |                  | jag_node_c81a1323ffbfdf60b3f240be5877ba437e8d85a79e11b0c72d40588c037868b9 | ^.+.tsx?$        | [object Object] | [object Object] | jsrg_node_78d7a67a648bdf2e14ebf6cf7b057d68561b4fc084020245cf3ce6e147802b3a |
| property-slot | [object Object] |                  | jag_node_c81a1323ffbfdf60b3f240be5877ba437e8d85a79e11b0c72d40588c037868b9 | 1                | [object Object] | [object Object] | jsrg_node_7c85bdf1b489c7959c8c1f10350738782de1c81d7b52646477f7b6d0951c5b5f |
| literal       | [object Object] |                  |                                                                           | "ts-jest"        | [object Object] | [object Object] | jsrg_node_96ec10e33ccdf65024473a412775d8dde9bbedca311fcf0c0430efe308552671 |
| expression    | [object Object] |                  |                                                                           | config           | [object Object] | [object Object] | jsrg_node_b58886862b0355d4c14276c084dc08c006362f894c6986144a902fa350feb01f |
| expression    | [object Object] |                  |                                                                           | import           | [object Object] | [object Object] | jsrg_node_c56f750e3c0e638594acbce9d9e4148a2f12a27bf5cf43adb4ce0f3c8ce9d4e0 |
| binding       | [object Object] |                  |                                                                           | config           | [object Object] | [object Object] | jsrg_node_e019095a7aa920fadcb5f2d899073116330abe84d531cc54e880928c27d2aef6 |
| property-slot | [object Object] |                  | jag_node_c81a1323ffbfdf60b3f240be5877ba437e8d85a79e11b0c72d40588c037868b9 | transform        | [object Object] | [object Object] | jsrg_node_eb93c403f257f81afaa2832c7bbb59a2f54aa0665aca96eb7facd00ad59e43a1 |
| expression    | [object Object] |                  |                                                                           | variable         | [object Object] | [object Object] | jsrg_node_ff15f08806f7d9f3ee0c3f8b8d72a6e6a8630fadda58b3a269a88bab87e1f747 |

## normalized_result.semantic_graph.relations

| source_node_id                                                             | target_node_id                                                             | relation        | resolution | properties      | evidence        | relation_id                                                                    |
|----------------------------------------------------------------------------|----------------------------------------------------------------------------|-----------------|------------|-----------------|-----------------|--------------------------------------------------------------------------------|
| jsrg_node_e019095a7aa920fadcb5f2d899073116330abe84d531cc54e880928c27d2aef6 | jsrg_node_00add50850f19a73a02d0afbd722c3489532af95fbef3c98dd1aaa2a3ed58426 | writes-property | resolved   | [object Object] | [object Object] | jsrg_relation_1b4ce9fe876bc3a0a56cc872942cf2bd4a917ed7c80dd68ed80fafcdb7b68652 |
| jsrg_node_c56f750e3c0e638594acbce9d9e4148a2f12a27bf5cf43adb4ce0f3c8ce9d4e0 | jsrg_node_0ec5cfb8621f14b24572472716dbcf3e0de8af145bdec50acfeeb59a758c5e48 | defines         | resolved   | [object Object] | [object Object] | jsrg_relation_1e41612ef66c902e9caf2e4835faa718c15003d19a00975369183a35386522d7 |
| jsrg_node_e019095a7aa920fadcb5f2d899073116330abe84d531cc54e880928c27d2aef6 | jsrg_node_eb93c403f257f81afaa2832c7bbb59a2f54aa0665aca96eb7facd00ad59e43a1 | writes-property | resolved   | [object Object] | [object Object] | jsrg_relation_35a13ad1065fbab7370ee331c955a751ab3ae0f475bb913f9e03ec02c7118162 |
| jsrg_node_e019095a7aa920fadcb5f2d899073116330abe84d531cc54e880928c27d2aef6 | jsrg_node_72ef8555edc820279c9dfcef32bf4b8929798fe0b77cd4222cb9a79cefc53de5 | writes-property | resolved   | [object Object] | [object Object] | jsrg_relation_4738bb6e21d7750e7f81892345f0a68e0d57ee7c5677ce116f8c49a471d7e28a |
| jsrg_node_eb93c403f257f81afaa2832c7bbb59a2f54aa0665aca96eb7facd00ad59e43a1 | jsrg_node_78d7a67a648bdf2e14ebf6cf7b057d68561b4fc084020245cf3ce6e147802b3a | writes-property | resolved   | [object Object] | [object Object] | jsrg_relation_6983ab6e0b26c98f8dfd623eb39ebbce279ba5b82cd62a46e83c08f80f293f6a |
| jsrg_node_78d7a67a648bdf2e14ebf6cf7b057d68561b4fc084020245cf3ce6e147802b3a | jsrg_node_760faa59006483572177459ff91d447cd1bb8f69825f7067c65473f4f199c1e5 | writes-property | resolved   | [object Object] | [object Object] | jsrg_relation_6f02fa0df88223e036186d6ed7cc1f469ee51a19810d2d612915b4ac0480f021 |
| jsrg_node_e019095a7aa920fadcb5f2d899073116330abe84d531cc54e880928c27d2aef6 | jsrg_node_b58886862b0355d4c14276c084dc08c006362f894c6986144a902fa350feb01f | reads           | resolved   | [object Object] | [object Object] | jsrg_relation_7b9f500aca31d751f472c3fc113e3932c56855de81bdb05f29984ffd07c1f074 |
| jsrg_node_0ec5cfb8621f14b24572472716dbcf3e0de8af145bdec50acfeeb59a758c5e48 | jsrg_node_250cbf5497b6e01d609dde0ffda0ca581ef7c96125f0f24eae0dd5d0e25174c9 | reads           | resolved   | [object Object] | [object Object] | jsrg_relation_89c43d03cfefb8aa4150fd8ce932b25c0e6ff02f6b51d487e257e6586966aa33 |
| jsrg_node_78d7a67a648bdf2e14ebf6cf7b057d68561b4fc084020245cf3ce6e147802b3a | jsrg_node_7c85bdf1b489c7959c8c1f10350738782de1c81d7b52646477f7b6d0951c5b5f | writes-property | resolved   | [object Object] | [object Object] | jsrg_relation_8acc7fda83e5ba479b58b181c2cc38de4fc182a86ba57e0d8bab7e0babea8e2e |
| jsrg_node_ff15f08806f7d9f3ee0c3f8b8d72a6e6a8630fadda58b3a269a88bab87e1f747 | jsrg_node_e019095a7aa920fadcb5f2d899073116330abe84d531cc54e880928c27d2aef6 | defines         | resolved   | [object Object] | [object Object] | jsrg_relation_a4e2e51d00ed7e2d0a08b2b163d2457a67e6c3359f7f65dfff6887cd0871c2e8 |
| jsrg_node_96ec10e33ccdf65024473a412775d8dde9bbedca311fcf0c0430efe308552671 | jsrg_node_760faa59006483572177459ff91d447cd1bb8f69825f7067c65473f4f199c1e5 | defines         | resolved   | [object Object] | [object Object] | jsrg_relation_e18e189c558e0aadb78a76a0d9618f11bac9ebd383e8c8fcee0f2e4dbc92ecda |
| jsrg_node_2370d5def5f808a6e543d712a5c600d05ddddf8eeb5eb8af31d4a509238b9ca1 | jsrg_node_00add50850f19a73a02d0afbd722c3489532af95fbef3c98dd1aaa2a3ed58426 | defines         | resolved   | [object Object] | [object Object] | jsrg_relation_e4e222d46e67b2784232e67de8412647d08db9f0112b5c7e83c6f4debbfc500a |
| jsrg_node_72ef8555edc820279c9dfcef32bf4b8929798fe0b77cd4222cb9a79cefc53de5 | jsrg_node_3042bbe69c4a1ed9864949393bdbfe53e7bbbb9e9ed6275be4f0c28e795a9a43 | writes-property | resolved   | [object Object] | [object Object] | jsrg_relation_eb50dd03e9ed8a28bf059a2672c9c2f0f871aafbe1038f8345ae740dc293cb1f |
| jsrg_node_29d6ee8e6d7d7b8d71cb4ba11e4556137fae42dbd7b846b770389e508e7aa3d2 | jsrg_node_3042bbe69c4a1ed9864949393bdbfe53e7bbbb9e9ed6275be4f0c28e795a9a43 | defines         | resolved   | [object Object] | [object Object] | jsrg_relation_f2cbed1f44974e0983ee8df9fee3a2d79045c2a78bf33251565cb21c1f2f4a44 |

## normalized_result.semantic_graph.fingerprints



## normalized_result.semantic_graph.unknowns

| node_id                                                                    | family    | relation_kinds | reason        | detail                                                                | candidate_node_ids                                                         | evidence        | unknown_id                                                                    |
|----------------------------------------------------------------------------|-----------|----------------|---------------|-----------------------------------------------------------------------|----------------------------------------------------------------------------|-----------------|-------------------------------------------------------------------------------|
| jsrg_node_0ec5cfb8621f14b24572472716dbcf3e0de8af145bdec50acfeeb59a758c5e48 | data-flow | defines        | unknown-value | Binding Config has no constant initializer. Unknown value at binding. | jsrg_node_0ec5cfb8621f14b24572472716dbcf3e0de8af145bdec50acfeeb59a758c5e48 | [object Object] | jsrg_unknown_848055742796261b77492f357f4101263a2dd9037db36fe728172d68b23db87a |

## normalized_result.semantic_graph.coverage.status

unknown

## normalized_result.semantic_graph.coverage.truncated

false

## normalized_result.semantic_graph.coverage.omitted_nodes

0

## normalized_result.semantic_graph.coverage.omitted_relations

0

## normalized_result.semantic_graph.coverage.limits



## normalized_result.semantic_graph.coverage.families

| family             | status  | retained_relations | omitted_relations | unknown_ids                                                                   |
|--------------------|---------|--------------------|-------------------|-------------------------------------------------------------------------------|
| boundary           | partial | 0                  | 0                 |                                                                               |
| call-flow          | partial | 0                  | 0                 |                                                                               |
| child-process      | partial | 0                  | 0                 |                                                                               |
| closure            | partial | 0                  | 0                 |                                                                               |
| configuration      | partial | 0                  | 0                 |                                                                               |
| data-flow          | partial | 7                  | 0                 | jsrg_unknown_848055742796261b77492f357f4101263a2dd9037db36fe728172d68b23db87a |
| event              | partial | 0                  | 0                 |                                                                               |
| object-flow        | partial | 7                  | 0                 |                                                                               |
| promise-ownership  | partial | 0                  | 0                 |                                                                               |
| request            | partial | 0                  | 0                 |                                                                               |
| resource-lifecycle | partial | 0                  | 0                 |                                                                               |
| timer              | partial | 0                  | 0                 |                                                                               |

## normalized_result.semantic_graph.limitations

Boundary extraction covers unshadowed JSON/global coercions plus parse and validation method candidates.,Child-process extraction covers asynchronous node:child_process creation, literal argv/env/stdio options, exit/error listeners, and kill signals.,Configuration extraction covers process.env, process.argv, node:fs reads, and direct logical defaults.,Event extraction covers EventEmitter-style literal registrations, removals, and dispatch candidates; dynamic names remain unknown.,Function fingerprints are static candidates; equal digests can remain ambiguous and do not prove behavioral equivalence.,Local data flow does not claim control-flow-sensitive reaching definitions or arbitrary dynamic property resolution.,Promise ownership covers explicit unshadowed Promise construction, static factories, aggregation, chaining, and await syntax only.,Request extraction covers fetch, WebSocket, node:http/node:https construction, direct option fields, and exact local response consumers.,Resource extraction covers built-in filesystem/network acquisition and exact local close/destroy/end handles.,The semantic graph contains static syntax observations and conservative relationship candidates; it does not claim runtime execution.,Timer extraction covers global or node:timers scheduling and exact local-handle cancellation.

## normalized_result.semantic_graph.graph_id

jsrg_8577ca23b4fb3561fc262ac06b4e4551a1ca444321043900467e0a88f3b8fc71

## confidence

derived

## authority

shipped-artifact

## environment

null

## limitations

CommonJS and ESM binding relationships were recovered from inert syntax and resolved only within the inventoried artifact container.,JavaScript and HTML were parsed as inert text; bundle bootstrap code was never executed.,Static imports, entrypoints, workers, endpoints, and storage relationships do not prove runtime execution.,Static paths and relationships may remain unresolved when expressions are dynamic or obfuscated.,Webpack/Rspack factories were recovered from AST literals; REA did not invoke push handlers or bundle bootstrap code.

## relationship_coverage

null

## locations

| kind          | path          |
|---------------|---------------|
| artifact-path | artifact-root |

## evidence_links

