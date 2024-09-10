import math
import random

def get_shot_parameters():
    """ Get shot parameters from the user. """
    angle = float(input("Enter the shooting angle (0 to 90 degrees): "))
    force = float(input("Enter the shooting force (1 to 10): "))
    return angle, force

def calculate_shot(angle, force):
    """ Calculate if the shot is successful based on angle and force. """
    # Convert angle to radians for trigonometric functions
    angle_rad = math.radians(angle)
    
    # Simulate the shot mechanics
    distance_to_hoop = 15  # Assume a standard basketball distance
    hoop_radius = 0.3  # Approximate radius of the hoop
    
    # Basic projectile motion formula
    horizontal_velocity = force * math.cos(angle_rad)
    vertical_velocity = force * math.sin(angle_rad)
    
    # Calculate time of flight and range
    time_of_flight = (2 * vertical_velocity) / 9.8
    range_of_shot = horizontal_velocity * time_of_flight
    
    # Randomize the accuracy of the shot
    accuracy = random.uniform(0.8, 1.2)
    range_of_shot *= accuracy
    
    # Check if the shot is successful
    if abs(range_of_shot - distance_to_hoop) <= hoop_radius:

