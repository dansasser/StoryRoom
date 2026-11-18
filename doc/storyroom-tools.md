# StoryRoom tool reference

The hosted connector exposes 88 tools to the assistant. Choose a row by what you want to do. The tool descriptions and input schemas exposed by the connected server give the exact parameters. In chat, you can ask for the operation in ordinary language.

| Task | Tools |
| --- | --- |
| Check service readiness and discover record schemas | `service_status`, `describe_story_resources`, `describe_story_type`, `describe_support_resource` |
| Create, find, update, or export a project | `create_project`, `list_projects`, `get_project`, `update_project`, `update_project_genre`, `get_project_activity`, `export_project` |
| Capture ideas and author records | `capture_idea`, `create_character`, `create_scene`, `create_story_object`, `list_story_objects`, `get_story_object`, `update_story_object`, `get_object_history`, `archive_story_object` |
| Manage supporting records and links | `list_support_records`, `create_support_record`, `update_support_record`, `delete_support_record` |
| Resume work, search, and check continuity | `get_story_context`, `search_story`, `search_story_semantic`, `search_story_relations`, `refresh_story_index`, `check_continuity` |
| Anchor a scene in time or inspect world state | `get_scene_anchor_candidates`, `anchor_scene_world_state`, `get_world_state`, `get_event_effects`, `compare_world_state`, `get_state_history`, `compare_perspectives`, `explain_world_state`, `transition_story_fact` |
| Decide canon and approve exact scene drafts | `propose_canon_change`, `approve_canon_proposal`, `reject_canon_proposal`, `save_scene_draft`, `get_scene_history`, `approve_scene_version`, `revoke_scene_approval` |
| Assemble and export a screenplay | `create_screenplay_assembly`, `list_screenplay_assemblies`, `get_screenplay_assembly`, `assemble_screenplay`, `list_assembly_versions`, `get_assembly_version`, `export_screenplay` |
| Open a visual interface | `open_story_workspace`, `open_relationship_graph`, `open_story_timeline` |
| Ingest, display, attach, and download images | `get_story_image_policy`, `save_story_image`, `set_workspace_profile_image`, `assign_workspace_profile_image`, `list_story_image_versions`, `view_story_image`, `display_story_image`, `download_story_image` |
| Describe, annotate, and retrieve visual references | `get_story_image_details`, `set_story_image_metadata`, `set_story_image_link`, `remove_story_image_link`, `set_story_image_region`, `view_story_image_region`, `search_story_images`, `search_story_images_by_similarity`, `refresh_story_image_index` |
| Establish geography, place objects, and edit terrain | `get_story_geography`, `save_story_geography`, `save_story_terrain_batch`, `preview_story_geography_rebuild`, `rebuild_story_geography` |
| Draw planning shapes, review boundaries, and stream the map | `get_story_geography_guides`, `preview_story_geography_guide`, `save_story_geography_guide`, `preview_story_location_extent`, `get_story_geography_render_index`, `read_story_geography_render_chunk` |
| Author, inspect, and export 3D models | `preview_story_spatial_change`, `read_story_spatial_scene`, `export_story_geometry`, `download_story_geometry`. Apply a reviewed model change through the geography save tool. |

## Operations inside the tools

- **Context.** `get_story_context` supports orientation, pinned project guidance, development overview, general and development context, the story bible, Timeline, and reveal map. Compact search returns evidence, match status, and a continuation when more results are available. [Story search](readme/story-workflows.md#find-a-record-and-check-its-evidence)
- **Time and perspective.** Use an event or anchored scene to compare objective facts, a character's beliefs or perceptions, and disclosures to the audience. A known-by event can bound a belief even when the acquisition event is unknown. State explanations name the supporting records or the missing evidence. [World-state queries](readme/story-workflows.md#compare-what-happened-with-who-knew)
- **Spatial authoring.** Read `spatial_capabilities` through the geography reader. Preview a batch containing `put_geometry`, `put_node`, `transition_node`, `reparent_node`, or `put_reference`. Review measurements and affected nodes, then apply the identical batch with its preview token using `commit_spatial`. The reader also exposes spatial assets, nodes, meshes, measurements, relations, and edit history. [Authoring examples and file formats](readme/geography-and-modeling.md#build-and-export-a-model)
- **Geography.** Define the coordinate frame, save placements and terrain, register an aerial reference, sample ground elevation, or inspect exact terrain triangles. Preview a location extent before committing it. Guides can be points, lines, or polygons with authored elevations or a terrain drape. [Geography controls](readme/geography-and-modeling.md#explore-the-map) · [Coordinate and terrain contracts](readme/geography-and-modeling.md#establish-a-coordinate-frame)
- **Images.** Search titles, metadata, and links, use semantic or text-to-image search, or find images similar to a particular saved version. Regions can identify details within an image with their own review status. [Visual search](readme/story-workflows.md#work-with-images)
- **Screenplays.** Archival, working, and approved assemblies pin exact scene versions. Read current or archived scene history, and export the pinned assembly as JSON, plain text, or Fountain when its drafts are in Fountain format. [Assembly and export rules](readme/story-workflows.md#assemble-and-export-a-screenplay)

## Available record types

The connected server lists 27 creative types and 25 supporting types. Use schema discovery before writing to a type. Ask “What fields does a scene have?” to see its schema in your connected project.

| Creative records | Types |
| --- | --- |
| Development | Ideas, decisions, open questions, tasks, change proposals, themes |
| Narrative structure | Acts, beats, sequences, scenes, timeline events, plot threads, setups and payoffs |
| People and the world | Characters, character relationships, organizations, locations, props and motifs, technologies, world rules |
| Knowledge and evidence | Story facts, beliefs, perception versions, reveals, research sources, creative references, in-world media |

| Supporting records | Types |
| --- | --- |
| Connections and evidence | Object links, object sources, source records, object tags, tags, assets, object assets |
| People, time, and disclosure | Character arc points, relationship changes, organization memberships, event participants, event presentations, reveal facts, reveal recipients |
| Scene construction | Scene beats, scene characters, scene components, scene props, plot-thread scenes |
| Review and production | Continuity issues, review comments, production notes, project packages, package items, registrations |

## Workspace actions

The visual interfaces use eight additional app-only tools. They load browse pages, graph links, timeline events, profile images, and thumbnails, and handle character edits and image uploads.

`get_workspace_page`, `save_workspace_character`, `get_relationship_graph`, `get_story_timeline_page`, `lookup_workspace_profile_images`, `read_workspace_image_chunk`, `stage_workspace_image_chunk`, `save_workspace_image_upload`.

## Optional development tools

Separately configured development environments can register these additional tools.

- **Development inbox** — `create_debug_message`, `list_debug_messages`, `read_debug_message`, `mark_debug_message_status`.
- **Codex handoff** — `save_codex_handoff`, `read_codex_handoff`.
