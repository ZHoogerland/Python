# Python

import csv
import pandas
import datetime
import calendar

chicago = pandas.read_csv('chicago.csv', parse_dates = ['Start Time', 'End Time'])
new_york_city = pandas.read_csv('new_york_city.csv', parse_dates = ['Start Time', 'End Time'])
washington = pandas.read_csv('washington.csv', parse_dates = ['Start Time', 'End Time'])

def get_city():
    '''Asks the user for a city and returns the filename for that city's bike share data.
    Args:
        none.
    Returns:
        (str) Filename for a city's bikeshare data.
    '''
    city = ''
    while city.lower() not in ['chicago', 'new york', 'washington']:
        city = input('\nHello! Let\'s explore some US bikeshare data!\n'
                     'Would you like to see data for Chicago, New York, or'
                     ' Washington?\n')
        if city.lower() == 'chicago':
            return 'chicago.csv'
        elif city.lower() == 'new york':
            return 'new_york_city.csv'
        elif city.lower() == 'washington':
            return 'washington.csv'
        else:
            print('Sorry, I do not understand your input. Please input either ''Chicago, New York, or Washington.')
