# Cr-a-D-co-Design-d-Int-rieur-G-n-ratif-par-IA
Créa-Déco utilise l'IA générative et la diffusion stable pour créer des designs d'intérieur personnalisés en fonction du style, des couleurs préférées et de l'agencement de l'espace des utilisateurs.
import random

# Simulated Database of Interior Design Elements
design_elements = {
    'modern': {'colors': ['black', 'white', 'gray'], 'furniture': ['minimalist sofa', 'abstract art', 'glass coffee table']},
    'vintage': {'colors': ['beige', 'light blue', 'ivory'], 'furniture': ['vintage armchair', 'classic bookshelf', 'retro lamp']},
    'bohemian': {'colors': ['turquoise', 'orange', 'brown'], 'furniture': ['boho chic rug', 'wicker basket', 'macrame wall hanging']}
}

def get_user_preferences():
    print("Welcome to Créa-Déco: Your AI-Powered Interior Design Assistant!\n")
    style = input("What style do you prefer? (Modern/Vintage/Bohemian): ").lower()
    color_preference = input("What's your preferred color scheme? (Provide any color): ").lower()
    layout = input("Describe your space layout briefly (e.g., large living room with big windows): ")
    
    return style, color_preference, layout

def generate_design(style, color_preference, layout):
    print("\nGenerating your personalized interior design...\n")
    
    # Simulating design generation logic
    design_plan = {
        'style': style.capitalize(),
        'colors': design_elements[style]['colors'] + [color_preference],
        'furniture': random.sample(design_elements[style]['furniture'], 2),
        'layout': layout,
        'additional_features': ['ambient lighting', 'indoor plants']  # Adding some common features to all styles
    }
    
    return design_plan

def display_design(design_plan):
    print("Here's your custom interior design plan:\n")
    print(f"Style: {design_plan['style']}")
    print(f"Color Scheme: {', '.join(design_plan['colors'])}")
    print(f"Furniture Selection: {', '.join(design_plan['furniture'])}")
    print(f"Layout Description: {design_plan['layout']}")
    print(f"Additional Features: {', '.join(design_plan['additional_features'])}")

def main():
    user_style, user_color, user_layout = get_user_preferences()
    if user_style in design_elements:
        design_plan = generate_design(user_style, user_color, user_layout)
        display_design(design_plan)
    else:
        print("Sorry, we currently do not support that style. Please choose from Modern, Vintage, or Bohemian.")

if __name__ == "__main__":
    main()
