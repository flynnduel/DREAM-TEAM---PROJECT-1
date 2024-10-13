# DREAM-TEAM---PROJECT-1

## Team Name
MIST 4610: 29704 - Dream Team

## Team Members
* Flynn Duel
* Anna Pachon
* Jeremiah Doherty
* Geetika Polkam
* Krutee Pillay

## Problem Description

## Data Model

## Data Dictionary

## Queries
### Complex 1
SELECT artist.artistname, SUM(inventory.quantityinstock) AS remaining_inventory FROM inventory

JOIN supplier_has_record 
ON inventory.supplier_has_record_record_idrecord = supplier_has_record.record_idrecord

JOIN record ON supplier_has_record.record_idrecord = record.idrecord

JOIN artist ON record.artist_idartist = artist.idartist

GROUP BY artist.artistname
ORDER BY remaining_inventory DESC;

### Complex 2

### Complex 3

### Complex 4

### Complex 5

### Complex 6

### Simple 1

# Simple 2

# Simple 3

# Simple 4
