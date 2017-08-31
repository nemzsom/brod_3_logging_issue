Empty project with brod 3.0.0 dependecy to illustrate the issue <https://github.com/klarna/brod/issues/227>

#### Running
Get the dependencies with
`mix deps.get`

Run with
`mix run`

#### Issue
When it is started it prints out these logs:
```

=PROGRESS REPORT==== 31-Aug-2017::07:13:38 ===
          supervisor: {local,sasl_safe_sup}
             started: [{pid,<0.152.0>},
                       {id,alarm_handler},
                       {mfargs,{alarm_handler,start_link,[]}},
                       {restart_type,permanent},
                       {shutdown,2000},
                       {child_type,worker}]

=PROGRESS REPORT==== 31-Aug-2017::07:13:38 ===
          supervisor: {local,sasl_sup}
             started: [{pid,<0.151.0>},
                       {id,sasl_safe_sup},
                       {mfargs,
                           {supervisor,start_link,
                               [{local,sasl_safe_sup},sasl,safe]}},
                       {restart_type,permanent},
                       {shutdown,infinity},
                       {child_type,supervisor}]

=PROGRESS REPORT==== 31-Aug-2017::07:13:38 ===
          supervisor: {local,sasl_sup}
             started: [{pid,<0.153.0>},
                       {id,release_handler},
                       {mfargs,{release_handler,start_link,[]}},
                       {restart_type,permanent},
                       {shutdown,2000},
                       {child_type,worker}]

=PROGRESS REPORT==== 31-Aug-2017::07:13:38 ===
         application: sasl
          started_at: nonode@nohost

=PROGRESS REPORT==== 31-Aug-2017::07:13:38 ===
         application: snappyer
          started_at: nonode@nohost

=PROGRESS REPORT==== 31-Aug-2017::07:13:38 ===
         application: kafka_protocol
          started_at: nonode@nohost

=PROGRESS REPORT==== 31-Aug-2017::07:13:38 ===
         application: supervisor3
          started_at: nonode@nohost

=PROGRESS REPORT==== 31-Aug-2017::07:13:38 ===
         application: brod
          started_at: nonode@nohost

=PROGRESS REPORT==== 31-Aug-2017::07:13:38 ===
         application: brod_3_logging_issue
          started_at: nonode@nohost
```

If the brod version is downgraded to 2.5.0 then it prints out nothing which is the expected behavior.

