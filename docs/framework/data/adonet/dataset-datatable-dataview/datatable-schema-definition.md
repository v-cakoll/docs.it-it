---
title: Definizione dello schema di DataTable
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: 81da3937b709d4ef046eb1c470546f168bde4132
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757762"
---
# <a name="datatable-schema-definition"></a>Definizione dello schema di DataTable
Lo schema, o struttura, di una tabella viene rappresentato da colonne e vincoli. Lo schema di un tipo <xref:System.Data.DataTable> viene definito usando gli oggetti <xref:System.Data.DataColumn> oltre agli oggetti <xref:System.Data.ForeignKeyConstraint> e <xref:System.Data.UniqueConstraint>. Le colonne di una tabella possono essere associate a colonne di un'origine dati, contenere valori calcolati da espressioni, incrementare automaticamente i propri valori o contenere valori di chiavi primarie.  
  
 I riferimenti basati sui nomi a colonne, relazioni e vincoli di una tabella distinguono tra maiuscole e minuscole. Pertanto, in una tabella possono coesistere due o più colonne, relazioni o vincoli con lo stesso nome ma che presentano una combinazione diversa di maiuscole e minuscole. Ad esempio, è possibile avere **Col1** e **col1**. In tal caso, è necessario che in un riferimento a una delle colonne basato sul nome venga usato il nome con la stessa combinazione di maiuscole e minuscole adottata nella colonna. Se il nome non corrisponde, verrà generata un'eccezione. Ad esempio, se la tabella **myTable** contiene le colonne **Col1** e **col1**, si fa riferimento a **Col1** in base al nome come  **Col1 "]**, e **col1** come **Col1"]**. Il tentativo di fare riferimento a colonne di **Col1 "]** verrà generata un'eccezione.  
  
 La distinzione tra maiuscole e minuscole non è rilevante se nella tabella è presente solo una colonna, una relazione o un vincolo con un determinato nome. Ovvero, se nella tabella non sono presenti altre relazioni o oggetti Constraint il cui nome corrisponda al nome della particolare colonna o relazione o oggetto Constraint, è possibile fare riferimento all'oggetto mediante il nome, usando sia lettere maiuscole che minuscole, senza che venga generata alcuna eccezione. Ad esempio, se la tabella include solo **Col1**, è possibile farvi riferimento tramite **personale. Colonne ["COL1"]**.  
  
> [!NOTE]
>  Il <xref:System.Data.DataTable.CaseSensitive%2A> proprietà del **DataTable** non influisce su tale comportamento. Il **CaseSensitive** proprietà si applica ai dati in una tabella e influisce sull'ordinamento, ricerca, filtro, vincoli e così via, ma non per i riferimenti a colonne, relazioni e vincoli.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Aggiunta di colonne a un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-columns-to-a-datatable.md)  
 Viene descritto come definire le colonne di una tabella tramite **DataColumn** oggetti.  
  
 [Creazione di colonne espressioni](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-expression-columns.md)  
 Viene illustrato come la **espressione** proprietà di una colonna può essere utilizzata per calcolare i valori in base ai valori di altre colonne nella riga.  
  
 [Creazione di colonne AutoIncrement](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)  
 Viene descritto come impostare una colonna in modo che incrementi automaticamente i valori numerici, per garantire un valore di colonna univoco per ogni riga.  
  
 [Definizione di chiavi primarie](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)  
 Viene descritto come specificare la chiave primaria di una tabella da uno o più **DataColumn** oggetti.  
  
 [Vincoli di DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)  
 Viene descritto come definire vincoli di chiave esterna e univoci per le colonne di una tabella.  
  
## <a name="see-also"></a>Vedere anche  
 [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
