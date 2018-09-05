---
title: Riepilogo del processo di inferenza dello schema dataset
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 1583d5232a3dd483bbe2a6fa0b1bc8a3ae6a659f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773367"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a>Riepilogo del processo di inferenza dello schema dataset
Il processo di inferenza determina innanzitutto, sulla base del documento XML, quali elementi verranno inferiti come tabelle. Sulla base delle rimanenti informazioni XML, il processo di inferenza consente quindi di determinare le colonne per tali tabelle. Nel caso di tabelle annidate, gli oggetti <xref:System.Data.DataRelation> e <xref:System.Data.ForeignKeyConstraint> vengono generati dal processo di inferenza.  
  
 Di seguito viene riportato un breve riepilogo delle regole di inferenza:  
  
-   Gli elementi a cui sono associati attributi vengono inferiti come tabelle.  
  
-   Gli elementi a cui sono associati elementi figlio vengono inferiti come tabelle.  
  
-   Gli elementi ripetuti vengono inferiti come tabella singola.  
  
-   Se all'elemento del documento, o radice, non sono associati attributi ed elementi figlio da inferire come colonne, tale elemento viene inferito come un tipo <xref:System.Data.DataSet>. In caso contrario, l'elemento del documento viene inferito come tabella.  
  
-   Gli attributi vengono inferiti come colonne.  
  
-   Gli elementi a cui non sono associati attributi o elementi figlio e che non si ripetono vengono inferiti come colonne.  
  
-   Per gli elementi che vengono inferiti come tabelle annidate all'interno di altri elementi inferiti come tabelle, nidificate **DataRelation** viene creato tra le due tabelle. Una nuova colonna di chiave primaria denominata **TableName_Id** vengono aggiunti a entrambe le tabelle e usata per il **DataRelation**. Oggetto **ForeignKeyConstraint** viene creato tra le due tabelle utilizzando il **TableName_Id** colonna.  
  
-   Per gli elementi che vengono inferiti come tabelle e contenenti testo ma non elementi figlio, una nuova colonna denominata **TableName_Text** viene creato per il testo della ognuno degli elementi. Se un elemento viene inferito come tabella e dispone di testo, ma a tale elemento sono associati anche elementi figlio, il testo verrà ignorato.  
  
## <a name="see-also"></a>Vedere anche  
 [Deduzione della struttura relazionale di DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Caricamento di un oggetto DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Caricamento delle informazioni dello schema DataSet da XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
