Main focus of the project is to estimate total time which is needed to complete a fire technical documentation project.

About dataset: 

There are data for every project that I have conducted at my job as a fire technical consultant in civil engineering (for a year 2019). 
Most of the fire technical documentation projects were small or medium-sized.
Datasets consist of following features:

    name: name of the project
    time: time needed to coplete the project (source: Toggl)
    price: price for each project
    system: link to the main fire technical documentation feature describing constructions, 1 - non-flammable, 2 - mixed, 3 - non-flammable
    height: Fire height of the building - measured from the floor of first flor up to the floor of the last floor
    area: Area of focus in m2
    area_floor_total: total floor area in m2
    area_floor_drawings: area in m2 which is being drawn
    num_of_floors: number of floors in total
    change: feature describing whether the new building is beeing assesed or the old one. Feature also express the magnitude of change, 1 - small changes in any building, 2 - medium-sized changes in old building, 3 - large-sized changes in old buildings, 4 - medium or large changes in new buildings (1977 or later)
    num_sections: number of fire sections in the building
    num_special: number of special calculations in the assesment (fire separations, detailed calculations etc.)
    block_plan: logical value whether the project has a block plan conducted
    n_drawings: number of drawings other than block plan


Main focus:

Main focus is to estimate time which is needed to conduct a fire technical documentation project.
Linear regression is used in the project


Results:

Last cell in the jupyter notebook can be used to produce time estimation for a project based on following features:

    'area_floor_total'
    'area_floor_drawings'
    'num_sections'
    'num_special'
    'block_plan'
    'n_drawings'

The regression model shows good R2 score for both train (.986) and test (0.806) data.
Model suffers from lack of large amount of data especialy from the large scale projects. 
Some larger projects therefore tends to place far away from the regression line, corrupting the final score.
This is particulary noticible from the last residual plot (multiple_polynomial model),
where the R2 score is corrupted by clear outliers.

Future work:

    - add more data to the model (data for a year 2017, 2018 and 2020) 
    - deal with outliers that are reducing the R2 score
