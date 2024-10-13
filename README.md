# DREAM-TEAM---PROJECT-1

## Team Name
MIST 4610: 29704 - Dream Team

## Team Members
1. Flynn Duel 
2. Anna Pachon
3. Jeremiah Doherty
4. Geetika Polkam
5. Krutee Pillay

## Problem Description

## Data Model
<blockquote class="imgur-embed-pub" lang="en" data-id="a/3QwgzIk"  ><a href="//imgur.com/a/3QwgzIk">Data Model</a></blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script>
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
