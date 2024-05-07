# Premier League Analysis

This project involves analyzing football league data from the English Premier League, including team standings, points, goals scored, and other metrics. It utilizes the Football API from API Sports to fetch data for a specified range of years, processes the data using pandas, and generates visualizations to analyze team performance over time.

## Requirements

- API key from https://www.api-football.com/
- pandas
- json
- http.client
- matplotlib
- numpy

## Functions

### `create_dataframe(yearfrom, yearto, API_key)`

- Creates a DataFrame from the standings data for a specified range of years.
- Parameters:
  - `yearfrom (int)`: Starting year.
  - `yearto (int)`: Ending year.
  - `API_key (str)`: API key for accessing the football API.
- Returns:
  - `df_list (list)`: List of DataFrames, each containing standings data for one season.

### `split_columns(lst)`

- Splits columns containing nested JSON objects into separate DataFrames and combines them with the original DataFrame.
- Parameters:
  - `lst (list)`: A list of pandas DataFrames where each DataFrame contains columns with nested JSON objects.
- Returns:
  - `list`: A list of pandas DataFrames with split columns combined with the original DataFrames.

### `drop_columns(lst)`

- Drops specified columns from each DataFrame in a list of DataFrames.
- Parameters:
  - `lst (list)`: A list of pandas DataFrames.
- Returns:
  - `list`: A list of pandas DataFrames with specified columns dropped.

### `column_names(df_list)`

- Cleans a list of DataFrames by selecting specific columns.
- Parameters:
  - `df_list (list)`: List of DataFrames to be cleaned.
- Returns:
  - `DataFrame`: The final cleaned DataFrame.

### `make_big_df(df_list, fromyear, toyear)`

- Concatenates DataFrames from a list into a single DataFrame and adds a 'season' column.
- Parameters:
  - `df_list (list)`: List of DataFrames to be concatenated.
  - `fromyear (int)`: Starting year.
  - `toyear (int)`: Ending year.
- Returns:
  - `DataFrame`: The concatenated DataFrame with a 'season' column.

### `plot_top_teams_position(pl, num_teams=6, figsize=(10, 6), save_path=None)`

- Plots the league position per season for the top N teams.
- Parameters:
  - `pl (DataFrame)`: DataFrame containing the league position data.
  - `num_teams (int)`: Number of top teams to include in the plot.
  - `figsize (tuple)`: Figure size (width, height) in inches.
  - `save_path (str)`: Path to save the plot (including filename and extension).
- Returns:
  - `None`

### `plot_top_teams_points(pl, num_teams=6, figsize=(10, 6), save_path=None)`

- Plots the points per season for the top N teams.
- Parameters:
  - `pl (DataFrame)`: DataFrame containing the points data.
  - `num_teams (int)`: Number of top teams to include in the plot.
  - `figsize (tuple)`: Figure size (width, height) in inches.
  - `save_path (str)`: Path to save the plot (including filename and extension).
- Returns:
  - `None`

### `plot_team_goal_difference(pl, team_name, figsize=(10, 6), save_path=None)`

- Plots the goal difference per season for a specific team.
- Parameters:
  - `pl (DataFrame)`: DataFrame containing the league position data.
  - `team_name (str)`: Name of the team to plot the goal difference for.
  - `figsize (tuple)`: Figure size (width, height) in inches.
  - `save_path (str)`: Path to save the plot (including filename and extension).
- Returns:
  - `None`

### `plot_team_goal_difference_and_points(pl, team_name, figsize=(10, 6), save_path=None)`

- Plots the goal difference and points per season for a specific team.
- Parameters:
  - `pl (DataFrame)`: DataFrame containing the league position data.
  - `team_name (str)`: Name of the team to plot the goal difference and points for.
  - `figsize (tuple)`: Figure size (width, height) in inches.
  - `save_path (str)`: Path to save the plot (including filename and extension).
- Returns:
  - `None`

### `plot_team_goals_home_away(pl, team_name, figsize=(10, 6), save_path=None)`

- Plots the total goals scored and conceded per season for a specific team.
- Parameters:
  - `pl (DataFrame)`: DataFrame containing the league position data.
  - `team_name (str)`: Name of the team to plot the goals for.
  - `figsize (tuple)`: Figure size (width, height) in inches.
  - `save_path (str)`: Path to save the plot (including filename and extension).
- Returns:
  - `None`

### `plot_team_win_rate(pl, team_name, figsize=(8, 6), save_path=None)`

- Plots the win rate for home and away games per season for a specific team.
- Parameters:
  - `pl (DataFrame)`: DataFrame containing the league position data.
  - `team_name (str)`: Name of the team to plot the win rate for.
  - `figsize (tuple)`: Figure size (width, height) in inches.
  - `save_path (str)`: Path to save the plot (including filename and extension).
- Returns:
  - `None`

### `plot_team_placement_vs_points(pl, team_name, figsize=(8, 6), save_path=None)`

- Plots the league placement vs points per season for a specific team.
- Parameters:
  - `pl (DataFrame)`: DataFrame containing the league position data.
  - `team_name (str)`: Name of the team to plot the data for.
  - `figsize (tuple)`: Figure size (width, height) in inches.
  - `save_path (str)`: Path to save the plot (including filename and extension).
- Returns:
  - `None`

### `plot_team_goals(pl, team_name, figsize=(10, 6), save_path=None)`

- Plots the goals scored and conceded per season for a specific team.
- Parameters:
  - `pl (DataFrame)`: DataFrame containing the league position data.
  - `team_name (str)`: Name of the team to plot the data for.
  - `figsize (tuple)`: Figure size (width, height) in inches.
  - `save_path (str)`: Path to save the plot (including filename and extension).
- Returns:
  - `None`

## Usage

1. Set up your API key for accessing the football API.
2. Call the `create_dataframe` function to fetch the data for a specific range of years.
3. Clean and process the data using the provided functions.
4. Generate visualizations using the plotting functions.
