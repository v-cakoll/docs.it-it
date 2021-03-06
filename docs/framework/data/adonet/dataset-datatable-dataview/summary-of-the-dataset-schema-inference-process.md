---
title: Riepilogo del processo di inferenza dello schema dataset
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 35e9b67d2d0a47aa69eabdb4b7e94f95b0b9589f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833976"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a>Riepilogo del processo di inferenza dello schema dataset
Il processo di inferenza determina innanzitutto, sulla base del documento XML, quali elementi verranno inferiti come tabelle. Sulla base delle rimanenti informazioni XML, il processo di inferenza consente quindi di determinare le colonne per tali tabelle. Nel caso di tabelle annidate, gli oggetti <xref:System.Data.DataRelation> e <xref:System.Data.ForeignKeyConstraint> vengono generati dal processo di inferenza.  
  
 Di seguito è riportato un breve riepilogo delle regole di inferenza:  
  
- Gli elementi a cui sono associati attributi vengono inferiti come tabelle.  
  
- Gli elementi a cui sono associati elementi figlio vengono inferiti come tabelle.  
  
- Gli elementi ripetuti vengono inferiti come tabella singola.  
  
- Se all'elemento del documento, o radice, non sono associati attributi ed elementi figlio da inferire come colonne, tale elemento viene inferito come un tipo <xref:System.Data.DataSet>. In caso contrario, l'elemento del documento viene inferito come tabella.  
  
- Gli attributi vengono inferiti come colonne.  
  
- Gli elementi a cui non sono associati attributi o elementi figlio e che non si ripetono vengono inferiti come colonne.  
  
- Per gli elementi inferiti come tabelle nidificate all'interno di altri elementi inferiti come tabelle, viene creata una **DataRelation** annidata tra le due tabelle. Una nuova colonna chiave primaria denominata **TableName_Id** viene aggiunta a entrambe le tabelle e utilizzata da **DataRelation**. Viene creato un **vincolo ForeignKeyConstraint** tra le due tabelle usando la colonna **TableName_Id** .  
  
- Per gli elementi inferiti come tabelle e che contengono testo ma privi di elementi figlio, viene creata una nuova colonna denominata **TableName_Text** per il testo di ogni elemento. Se un elemento viene inferito come tabella e dispone di testo, ma a tale elemento sono associati anche elementi figlio, il testo verrà ignorato.  
  
## <a name="see-also"></a>Vedere anche

- [Deduzione della struttura relazionale di DataSet da XML](inferring-dataset-relational-structure-from-xml.md)
- [Caricamento di un oggetto DataSet da XML](loading-a-dataset-from-xml.md)
- [Caricamento delle informazioni dello schema DataSet da XML](loading-dataset-schema-information-from-xml.md)
- [Uso di XML in un set di dati](using-xml-in-a-dataset.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
