---

database-plugin: basic

---

```yaml:dbfolder
name: new database
description: new description
columns:
  column1:
    input: text
    key: column1
    accessorKey: column1
    label: Column 1
    position: 1
    skipPersist: false
    isHidden: true
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  __file__:
    key: __file__
    id: __file__
    input: markdown
    label: File
    accessorKey: __file__
    isMetadata: true
    skipPersist: false
    isDragDisabled: false
    csvCandidate: true
    position: 2
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: true
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      wrap_content: true
  status:
    input: select
    accessorKey: status
    key: status
    id: newColumn2
    label: Status
    position: 4
    skipPersist: false
    isHidden: false
    sortIndex: 0
    isSorted: true
    isSortedDesc: false
    options:
      - { label: "2 To Do", value: "2_todo", color: "hsl(135, 95%, 90%)"}
      - { label: "1 Next Up", value: "1_nextup", color: "hsl(7, 95%, 90%)"}
      - { label: "4 Waiting For", value: "4_waitingfor", color: "hsl(60,77%,66%)"}
      - { label: "0 Inbox", value: "0_inbox", color: "hsl(0,0%,91%)"}
      - { label: "5 Ferment", value: "5_ferment", color: "hsl(204, 95%, 90%)"}
      - { label: "6 Done", value: "6_done", color: "hsl(0,0%,36%)"}
      - { label: "3 Doing", value: "3_doing", color: "hsl(300, 95%, 90%)"}
      - { label: "7 Cancelled", value: "7_cancelled", color: "hsl(251, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      option_source: manual
  date:
    input: calendar
    accessorKey: date
    key: date
    id: date
    label: Start Date
    position: 5
    skipPersist: false
    isHidden: false
    sortIndex: -1
    isSorted: false
    isSortedDesc: true
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  context:
    input: tags
    accessorKey: context
    key: context
    id: context
    label: Context
    position: 7
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 147
    options:
      - { label: "quiet", value: "quiet", color: "hsl(256, 95%, 90%)"}
      - { label: "computer", value: "computer", color: "hsl(84, 95%, 90%)"}
      - { label: "phone", value: "phone", color: "hsl(238, 95%, 90%)"}
      - { label: "LINE", value: "LINE", color: "hsl(261, 95%, 90%)"}
      - { label: "facebook", value: "facebook", color: "hsl(238, 95%, 90%)"}
      - { label: "SoochowU", value: "SoochowU", color: "hsl(227, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      option_source: manual
  people:
    input: tags
    accessorKey: people
    key: people
    id: people
    label: People
    position: 11
    skipPersist: false
    isHidden: false
    sortIndex: -1
    width: 112
    options:
      - { label: "蘇仰志", value: "蘇仰志", color: "hsl(85, 95%, 90%)"}
      - { label: "Megha Sarmah", value: "Megha Sarmah", color: "hsl(262, 95%, 90%)"}
      - { label: "北見秀司", value: "北見秀司", color: "hsl(329, 95%, 90%)"}
      - { label: "Christopher Day", value: "Christopher Day", color: "hsl(152, 95%, 90%)"}
      - { label: "{ endDate: April 14, 2023 }", value: "{ endDate: April 14, 2023 }", color: "hsl(178, 95%, 90%)"}
      - { label: "閉恩濡", value: "閉恩濡", color: "hsl(354, 95%, 90%)"}
      - { label: "米建國", value: "米建國", color: "hsl(116, 95%, 90%)"}
      - { label: "周大興", value: "周大興", color: "hsl(196, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  goals:
    input: tags
    accessorKey: goals
    key: goals
    id: goals
    label: Goals
    position: 8
    skipPersist: false
    isHidden: false
    sortIndex: -1
    options:
      - { label: "Master's Degree", value: "Master's Degree", color: "hsl(354, 95%, 90%)"}
      - { label: "學問之路", value: "學問之路", color: "hsl(172, 95%, 90%)"}
      - { label: "Allocation Dependence", value: "Allocation Dependence", color: "hsl(14, 95%, 90%)"}
      - { label: "Money Dependence", value: "Money Dependence", color: "hsl(241, 95%, 90%)"}
      - { label: "Controllability Dependence", value: "Controllability Dependence", color: "hsl(245, 95%, 90%)"}
      - { label: "Learning by Caring", value: "Learning by Caring", color: "hsl(355, 95%, 90%)"}
      - { label: "Care-Passion-Talent Model", value: "Care-Passion-Talent Model", color: "hsl(160, 95%, 90%)"}
      - { label: "Relfexive Media", value: "Relfexive Media", color: "hsl(275, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  Project:
    input: tags
    accessorKey: Project
    key: Project
    id: Project
    label: Project
    position: 9
    skipPersist: false
    isHidden: false
    sortIndex: -1
    options:
      - { label: "KASpaces", value: "KASpaces", color: "hsl(86, 95%, 90%)"}
      - { label: "雜學校", value: "雜學校", color: "hsl(231, 95%, 90%)"}
      - { label: "総合人間学会", value: "総合人間学会", color: "hsl(83, 95%, 90%)"}
      - { label: "IDEC", value: "IDEC", color: "hsl(102, 95%, 90%)"}
      - { label: "critical realism", value: "critical realism", color: "hsl(208, 95%, 90%)"}
      - { label: "碩論", value: "碩論", color: "hsl(217, 95%, 90%)"}
      - { label: "IACR 2023", value: "IACR 2023", color: "hsl(259, 95%, 90%)"}
      - { label: "KAS CTeC", value: "KAS CTeC", color: "hsl(291, 95%, 90%)"}
      - { label: "唯物論研究協会", value: "唯物論研究協会", color: "hsl(111, 95%, 90%)"}
      - { label: "JCR Judgemental Rationality", value: "JCR Judgemental Rationality", color: "hsl(49, 95%, 90%)"}
      - { label: "青醒人行政", value: "青醒人行政", color: "hsl(196, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  waitingfor:
    input: text
    accessorKey: waitingfor
    key: waitingfor
    id: waitingfor
    label: Waiting For
    position: 10
    skipPersist: false
    isHidden: false
    sortIndex: -1
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  endDate:
    input: calendar
    accessorKey: endDate
    key: endDate
    id: endDate
    label: Due/End Date
    position: 6
    skipPersist: false
    isHidden: false
    sortIndex: 2
    isSorted: true
    isSortedDesc: false
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
  priority:
    input: select
    accessorKey: priority
    key: priority
    id: Priority
    label: Priority
    position: 3
    skipPersist: false
    isHidden: false
    sortIndex: 3
    isSorted: true
    isSortedDesc: false
    options:
      - { label: "1", value: "1", color: "hsl(322, 95%, 90%)"}
      - { label: "2", value: "2", color: "hsl(73, 95%, 90%)"}
      - { label: "4", value: "4", color: "hsl(293, 95%, 90%)"}
      - { label: "3", value: "3", color: "hsl(26, 95%, 90%)"}
      - { label: "5", value: "5", color: "hsl(25, 95%, 90%)"}
    config:
      enable_media_view: true
      link_alias_enabled: true
      media_width: 100
      media_height: 100
      isInline: false
      task_hide_completed: true
      footer_type: none
      persist_changes: false
      option_source: manual
config:
  remove_field_when_delete_column: false
  cell_size: normal
  sticky_first_column: true
  group_folder_column: 
  remove_empty_folders: false
  automatically_group_files: false
  hoist_files_with_empty_attributes: false
  show_metadata_created: false
  show_metadata_modified: false
  show_metadata_tasks: false
  show_metadata_inlinks: false
  show_metadata_outlinks: false
  show_metadata_tags: false
  source_data: current_folder
  source_form_result: 
  source_destination_path: /
  row_templates_folder: /
  current_row_template: 
  pagination_size: 10
  font_size: 16
  enable_js_formulas: false
  formula_folder_path: /
  inline_default: false
  inline_new_position: last_field
  date_format: yyyy-MM-dd
  datetime_format: "yyyy-MM-dd HH:mm:ss"
  metadata_date_format: "yyyy-MM-dd HH:mm:ss"
  enable_footer: false
  implementation: default
filters:
  enabled: true
  conditions:
      - condition: AND
        disabled: false
        label: "0 Inbox"
        color: "hsl(0,0%,71%)"
        filters:
        - field: status
          operator: EQUAL
          value: "0_inbox"
          type: select
      - condition: AND
        disabled: true
        label: "1 Next Up"
        color: "hsl(96, 95%, 90%)"
        filters:
        - field: status
          operator: EQUAL
          value: "1_nextup"
          type: select
      - condition: AND
        disabled: true
        label: "2 To Do"
        color: "hsl(168, 95%, 90%)"
        filters:
        - field: status
          operator: EQUAL
          value: "2_todo"
          type: select
      - condition: AND
        disabled: true
        label: "3 Doing"
        color: "hsl(145, 95%, 90%)"
        filters:
        - field: status
          operator: EQUAL
          value: "3_doing"
          type: select
      - condition: AND
        disabled: true
        label: "4 Waiting For"
        color: "hsl(29, 95%, 90%)"
        filters:
        - field: status
          operator: EQUAL
          value: "4_waitingfor"
          type: select
      - condition: AND
        disabled: true
        label: "5 Ferment"
        color: "hsl(76, 95%, 90%)"
        filters:
        - field: status
          operator: EQUAL
          value: "5_ferment"
          type: select
      - condition: AND
        disabled: true
        label: "6 Done"
        color: "hsl(35, 95%, 90%)"
        filters:
        - field: status
          operator: EQUAL
          value: "6_done"
          type: select
```