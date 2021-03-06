# SchedJulia

SchedJulia is an appointment scheduling script written in Julia.

## Overview

SchedJulia uses the concept of appointments with required duration and attendees, crossed with the attendees' availabilities to produce a satisfying schedule.

### Prerequisites

- [Julia](https://julialang.org/)
- If you're interfacing with a calendar or spreadsheet, it's recommended that you write your own wrapper scripts when interfacing before and after running SchedJulia.
  - This way, the integer units representing time and be converted to real time expressions.
  - For example, [UTMIST's Scheduler](https://gitlab.com/utmist/utmist-scheduler).

### Files

- SchedJulia uses integer units to represent time. Of course, these units can be scaled to represent different timeslots of the time period.
  - For example, the range `[0-23]` can be used to represent the 24 hours in one day.
- Appointments to be scheduled include their unit duration and attendees, stored in `data/appointments.txt`.

  ```txt
  <appointment_name>|<duration>|<attendee>,<attendee>,...
  ...
  ```

- Availabilities of individual attendees are stored in `data/availability.txt`.

  ```txt
  <attendee>|<timeslot>,<timeslot>,...
  ...
  ```

- Follow the format of the above templates or example files closely, and do not include newlines at the end of the files.

## Usage

After loading `data/appointments.txt` and `data/availability.txt`, run the script.

```sh
julia schedjulia.jl
```

### Output

If a successful schedule arrangement is found, the output will be in `data/schedule.txt`, in the following format.

```txt
<appointment_name>|<start_time>-<end_time>|<attendee>,<attendee>,...
...
```

If no successful arrangement can be found, SchedJulia will output "`NO SCHEDULE POSSIBLE`".

## Development/Pages

- [**Homepage**](https://leglesslamb.gitlab.io/post/schedjulia)
- [**GitLab**](https://gitlab.com/leglesslamb/schedjulia)
  - Working issues and Merge Requests (MRs) are reviewed.
  - Bug reports and feature requests are preferred.
- [**GitHub (Mirror)**](https://github.com/leglesslamb/schedjulia)
  - Bug reports and feature requests are accepted.
