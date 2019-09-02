---
title: Definizione dello schema di DataTable
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: 0d2609801da3bc336c54d32068246027cfd6d3aa
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204985"
---
# <a name="datatable-schema-definition"></a>Definizione dello schema di DataTable
Lo schema, o struttura, di una tabella viene rappresentato da colonne e vincoli. Lo schema di un tipo <xref:System.Data.DataTable> viene definito usando gli oggetti <xref:System.Data.DataColumn> oltre agli oggetti <xref:System.Data.ForeignKeyConstraint> e <xref:System.Data.UniqueConstraint>. Le colonne di una tabella possono essere associate a colonne di un'origine dati, contenere valori calcolati da espressioni, incrementare automaticamente i propri valori o contenere valori di chiavi primarie.  
  
 I riferimenti basati sui nomi a colonne, relazioni e vincoli di una tabella distinguono tra maiuscole e minuscole. Pertanto, in una tabella possono coesistere due o più colonne, relazioni o vincoli con lo stesso nome ma che presentano una combinazione diversa di maiuscole e minuscole. Ad esempio, è possibile avere **col1** e **col1**. In tal caso, è necessario che in un riferimento a una delle colonne basato sul nome venga usato il nome con la stessa combinazione di maiuscole e minuscole adottata nella colonna. Se il nome non corrisponde, verrà generata un'eccezione. Se, ad esempio, nella tabella MyTable sono contenute le colonne **col1** e **col1**, è necessario fare riferimento a **col1** in base al nome **MyTable. Columns ["col1"]** e **col1** come **MyTable. Columns ["col1"]** . Il tentativo di fare riferimento a una delle colonne come **MyTable. Columns ["col1"]** genererebbe un'eccezione.  
  
 La distinzione tra maiuscole e minuscole non è rilevante se nella tabella è presente solo una colonna, una relazione o un vincolo con un determinato nome. Ovvero, se nella tabella non sono presenti altre relazioni o oggetti Constraint il cui nome corrisponda al nome della particolare colonna o relazione o oggetto Constraint, è possibile fare riferimento all'oggetto mediante il nome, usando sia lettere maiuscole che minuscole, senza che venga generata alcuna eccezione. Se, ad esempio, la tabella include solo **col1**, è possibile farvi riferimento usando **My. Colonne ["COL1"]** .  
  
> [!NOTE]
> La <xref:System.Data.DataTable.CaseSensitive%2A> proprietà di **DataTable** non influisce su questo comportamento. La proprietà **CaseSensitive** si applica ai dati di una tabella e influiscono sull'ordinamento, la ricerca, l'applicazione di filtri, l'applicazione di vincoli e così via, ma non i riferimenti a colonne, relazioni e vincoli.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Aggiunta di colonne a un oggetto DataTable](adding-columns-to-a-datatable.md)  
 Viene descritto come definire le colonne di una tabella utilizzando oggetti **DataColumn** .  
  
 [Creazione di colonne espressioni](creating-expression-columns.md)  
 Viene illustrato come utilizzare la proprietà **Expression** di una colonna per calcolare i valori in base ai valori di altre colonne della riga.  
  
 [Creazione di colonne AutoIncrement](creating-autoincrement-columns.md)  
 Viene descritto come impostare una colonna in modo che incrementi automaticamente i valori numerici, per garantire un valore di colonna univoco per ogni riga.  
  
 [Definizione di chiavi primarie](defining-primary-keys.md)  
 Viene descritto come specificare la chiave primaria di una tabella da uno o più oggetti **DataColumn** .  
  
 [Vincoli di DataTable](datatable-constraints.md)  
 Viene descritto come definire vincoli di chiave esterna e univoci per le colonne di una tabella.  
  
## <a name="see-also"></a>Vedere anche

- [DataTable](datatables.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
