NWB Notes.

# Standardization

Units standardization:
- time
    - make sure we condensing down to use the same, consistent & accurate clock
    - NWB files uses seconds by convention (I think). We need to make sure to standardize to this.
- voltage
    - NWB files uses volte by convention (I think). We need to make sure to standardize to this.

# METADATA

## Subject Information

The following goes into a `Subject` object:

- age, sex, description (epilepsy diag?), subject_id

## Session Information

The following is used to initialize the NWB file:

- identifier, experimenter, lab, institution, session_id, session_description, session_start_time

## Device (Electrode) Information

Recording equipment is defined as a 'Device'
Electrodes are defined in 'ElectrodeGroup' and 'Electrode'.
Open question: how to organize electrodes into groups

The following is used to initialize a device:
- device_name, device_description, device_manufacturer, location

The following is used to initialize an ElectrodeGroup:
- electrode_name, electrode_description, location

The following is used to initialize an Electrode:
- x_pos, y_pos, z_pos, impedence, location, filtering, reference
Note that an electrode is defined within a specified ElectrodeGroup

## Stimuli

We don't have conventional 'stimuli', but the relevant equivalent is, I think, chest positions.
I think we probably want to encode `chest_position` into `Stimuli`.

Note: there are two chest positions, per session, that don't change, right?

## Behaviour - space

Can store the subjects position (XY points) in a `Position` object, which goes into acquisition.

Notes:
- The DF also has `linear_position` and `speed`.
    - I'm not sure what `linear_position` is?
    - Are these measures recorded or derived?
        - Depending on this, can potentially add to `acquisition`, or as a `ProcessingModule` (derived information)

## Behaviour - events

- Decision: which key events do we want to encode in the event definition?
    - Need to finish converting the current DF into events at specific moments in time (in so far as this makes sense)
- Candidates:
    - `trial_start` & `trial_end`: use `trial`. How many should there be?
    - `button_press`: add the button press
    - `choice_point`
    - `planned_turn`: is this what they are _supposed_ to do? (Or what they did?)
    - `turned_left` & `turned_right`: can we use `left_loop`, `left_stem`, etc to
    - `encoding_trial`, `retrieval_trial`: convert to a signal marker at the start of a trial?
    - `brakes`: what is this?
