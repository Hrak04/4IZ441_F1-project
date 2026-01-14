# Formula 1 Ontology

This repository contains an OWL ontology and sample data modeling Formula 1 seasons, races, drivers, teams, cars, and driver assignments.  
The project was created as a semestral assignment for the course **4IZ441**.

## Repository Structure

- **f1_project.ttl**  
  Ontology vocabulary defining the core concepts and relationships of Formula 1, including Driver, Team, Race, Season, and DriverAssignment.

- **f1_data.ttl**  
  Sample instance data described using the ontology.  
  The dataset covers multiple seasons (2010, 2016, 2024), including races, championship winners, and an example of a mid-season driver substitution.

- **queries.sparql**  
  Sample SPARQL queries demonstrating how the ontology can be queried.

## Sample SPARQL Queries

The repository contains three sample SPARQL queries, all of which return results over the provided data:

1. **Teams using substitute drivers in the 2024 season**  
   This query identifies teams that used more than two drivers during the 2024 season, demonstrating how the `DriverAssignment` class enables modeling mid-season substitutions (e.g., Ferrari using a substitute driver).

2. **Races won by Ferrari drivers in the 2024 season**  
   This query retrieves races from the 2024 season where a Ferrari driver won, showing the use of the `winnerAssignment` property to connect races to specific driver assignments.

3. **Drivers’ and constructors’ champions across seasons**  
   This query lists championship winners for all seasons in the dataset (2010, 2016, 2024), illustrating the use of functional properties to represent unique season champions.

## Modeling Notes

- Drivers are modeled as real-world persons (`Driver`), while their participation in a specific team and season is modeled using the `DriverAssignment` class.
- Driver numbers are associated with `DriverAssignment`, allowing the same driver to use different numbers in different seasons.
- Race winners are represented via the `winnerAssignment` property, linking each race to the exact driver assignment that won.
- The ontology reuses existing vocabularies such as FOAF and Schema.org where appropriate.

## Usage

The ontology and data can be opened in **Protégé**.  
To execute the sample SPARQL queries, load both `f1_project.ttl` and `f1_data.ttl`, then run the queries from `queries.sparql`.
