# Importing workouts and meal plans from Excel

HoopsHub can load gym programs, technical (basketball skill) programs, a
weekly training schedule and meal plans from an Excel file.

**Quickest start:** download a template, replace the example rows with your
own, and import it.

- [workout-template.xlsx](templates/workout-template.xlsx): gym and technical programs with a schedule
- [meal-template.xlsx](templates/meal-template.xlsx): a weekly meal plan

## How to import

1. Save your spreadsheet as **.xlsx**. Excel and Google Sheets
   (*File → Download → Microsoft Excel*) both work. Old `.xls` files must be
   re-saved as `.xlsx`.
2. Put the file on your phone (Files, Drive, OneDrive, Downloads…).
3. In HoopsHub, open the **Gym**, **Technical** or **Diet** page and tap the
   **import** button (the upload icon at the top).
4. Pick the file, check the preview, and confirm.

One file can hold workouts and meals together, on separate sheets. Whichever
page you import from, everything in the file is imported.

## General rules

- **The first row of each table must be the column headings.** HoopsHub finds
  columns by their heading text, so column order doesn't matter and extra
  columns are fine. Headings can be in English or Greek, and capitals and
  accents don't matter.
- A title or a few notes **above** the heading row is fine.
- **Leave a cell blank to repeat the value above it** (Program, Day, Date,
  Start, End, Type, Category for workouts; Day, Time, Slot, Meal for meals).
  Merged cells work the same way.
- Rows that start with **Total** are skipped.
- Every sheet in the file is read, so you can use several sheets.

## Workouts

### Columns

Only **Exercise** is required, plus at least one other recognised column.

| Column heading | Also accepted | What goes in it |
|---|---|---|
| **Exercise** | Exercises, Movement, Drill, Name, Activity | Exercise or drill name *(required)* |
| **Program** | Workout, Session, Routine, Plan, Block | Program name. Rows with the same program are grouped. |
| **Type** | Kind | `Gym` or `Technical` (see below) |
| **Sets** | Set, Rounds | `4`, or `4x8` for sets and reps in one cell |
| **Reps** | Repetitions, Duration, Minutes, Distance, Volume | `8`, `8-10`, `30 s`, `400 m`, or `4x8` |
| **Weight** | Load, Kg, Lbs, Intensity, 1RM | `80 kg`, `70%`, `Bodyweight` |
| **Rest** | Recovery | `90 s`, `2 min` |
| **Target** | Goal | e.g. `8/10 makes` |
| **Category** | Focus, Skill, Area, Muscle group | e.g. `Shooting`, `Legs` |
| **Notes** | Comments, Cues, Instructions | Any notes |
| **Day** | Weekday | `Monday` … `Sunday` (or `Mon`), for the schedule |
| **Date** | | A specific date, for the schedule |
| **Start** | Start time, Time, From | `18:00`, `6pm`, or a range like `18:00-19:30` |
| **End** | End time, Finish, Until, To | `19:30` |
| **Week** | | `1`, `2`… The program becomes "Week 1 · …" |

Any other column (e.g. *Tempo*, *RPE*, *Video*) is added to the exercise's
notes. Columns like *No*, *#*, *Done* or *Status* are ignored.

### Gym or Technical?

Each program goes to the **Gym** page unless it looks technical. It goes to
**Technical** when the **Type** column, the program name or the sheet name
contains a word like *technical, skill, drill, basketball, shooting,
handling, dribbling, finishing, footwork, layup* or *passing*.

To be sure, add a **Type** column and write `Gym` or `Technical`.

### Naming programs

The program name comes from the first of these that is present:

1. the **Program** column
2. a **Day** cell with more than a weekday in it, e.g. `Day 1 - Upper Body`
3. a heading row: a row with only one filled cell, e.g. `DAY 2 – PULL (Wednesday)`
4. the sheet name (or the title above the headings, if the sheet is still
   called "Sheet1")

Heading rows starting with **Warm-up, Main, Accessory, Finisher, Superset,
Circuit, Mobility, Cool-down** or **Stretch** don't start a new program. They
set the category of the exercises under them instead.

### Scheduling

Programs only appear in your week planner if a row has a day or date:

- **Day** (`Monday`): the session **repeats every week** on that day.
- **Date** (`14/10/2026`, `2026-10-14` or `14/10`): a **one-off** session on
  that date.
- **Start / End** set the time. Without them, sessions start at **18:00** and
  last **90 minutes**.

You can also put the day or date in the program name, a heading row or the
sheet name, e.g. a sheet called `Monday`.

### Example

| Program | Type | Day | Start | End | Exercise | Sets | Reps | Weight | Rest |
|---|---|---|---|---|---|---|---|---|---|
| Lower Body Strength | Gym | Monday | 18:00 | 19:30 | Back Squat | 4 | 6 | 80 kg | 2 min |
| | | | | | Romanian Deadlift | 3 | 8 | 60 kg | 90 s |
| Shooting Workout | Technical | Tuesday | 17:00 | | Free throws | 5 | 10 | | |
| | | | | | Catch and shoot | | 5x10 | | |

## Meal plans

### Columns

A meal table needs **Day** plus **Food** or **Meal**, and at least three
recognised columns in total.

| Column heading | Also accepted | What goes in it |
|---|---|---|
| **Day** | Weekday | `Monday` … `Sunday` *(required)* |
| **Food** | Ingredient, Item | One food per row |
| **Meal** | Dish, Recipe, Title | Name of the meal, e.g. `Oats bowl` |
| **Slot** | Meal time, Occasion | `Breakfast`, `Lunch`, `Snack`… |
| **Time** | When | `08:00` |
| **Amount** | Quantity, Qty, Grams, Portion, Serving | `80`, or `250 ml` |
| **Unit** | | `g`, `ml`, `pcs`… (default `g`) |
| **Calories** | Kcal, Energy | Number |
| **Protein** | | Grams |
| **Carbs** | Carbohydrates | Grams |
| **Fat** | Fats | Grams |

### How rows become meals

- **One row per food.** Leave Time, Slot and Meal blank on the following rows
  to add more foods to the same meal.
- A new **Time**, **Slot** or **Meal** value starts a new meal.
- Calories and macros can be on each food row or on just one row of the meal.
  They are added up either way.
- Write the **Day** once and leave it blank below. A row with only a day in it
  (e.g. `TUESDAY — TRAINING DAY`) also works as a day heading.
- A row with a single cell that isn't a day (e.g. `SHOPPING LIST`) ends the
  meal table, so you can keep other notes below it.

### Example

| Day | Time | Slot | Meal | Food | Amount | Unit | Calories | Protein | Carbs | Fat |
|---|---|---|---|---|---|---|---|---|---|---|
| Monday | 08:00 | Breakfast | Oats bowl | Oats | 80 | g | 300 | 10 | 54 | 6 |
| | | | | Milk | 250 | ml | 160 | 8 | 12 | 9 |
| | 13:00 | Lunch | Chicken & rice | Chicken breast | 150 | g | 250 | 46 | 0 | 5 |
| | | | | Rice (cooked) | 200 | g | 260 | 5 | 56 | 1 |

## Re-importing an updated plan

- **Programs** with the same name are **replaced** by the new version, and
  their scheduled sessions are updated. Sessions you added by hand are kept.
- **Meals:** each day in the file **replaces** that day's meals. Days not in
  the file are left alone.

## Troubleshooting

| Message | Fix |
|---|---|
| *Choose an .xlsx file* | Re-save the file as `.xlsx`. |
| *No header row with an Exercise column* | Make sure the heading row has an **Exercise** column and is within the first 30 rows. |
| *No workouts or meals found* | Check the heading names against the tables above. Meal tables need a **Day** column. |
| A program landed on the wrong page | Add a **Type** column with `Gym` or `Technical`. |
| Sessions missing from the planner | Add a **Day** or **Date** column. |
