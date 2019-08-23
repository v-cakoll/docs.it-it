---
title: 'Procedura: Generare il modello a oggetti in Visual Basic o C#'
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 5f2c2f99a5efeb3463ecf5bf401a6cf654845bb2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911972"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>Procedura: Generare il modello a oggetti in Visual Basic o C\#
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping di un modello a oggetti nel linguaggio di programmazione in uso a un database relazionale. Sono disponibili due strumenti per la generazione automatica di un C# Visual Basic o di un modello dai metadati di un database esistente.  
  
- Se si utilizza Visual Studio, è possibile utilizzare il Object Relational Designer per generare un modello a oggetti. In O/R Designer è disponibile un'interfaccia utente avanzata che consente di generare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] un modello a oggetti. Per altre informazioni, vedere [strumenti LINQ to SQL in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).
  
- Lo strumento della riga di comando SQLMetal. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
    > [!NOTE]
    > Se non si dispone di un database esistente e si desidera crearne uno da un modello a oggetti, è possibile creare il modello a oggetti usando l'editor di codice e <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. Per altre informazioni, vedere [Procedura: Creazione dinamica di un database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).  
  
 La documentazione relativa a Progettazione relazionale oggetti fornisce esempi su come generare un modello a C# oggetti o Visual Basic usando la finestra di progettazione di o/r. Le informazioni seguenti forniscono esempi relativi all'uso dello strumento della riga di comando SQLMetal. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Esempio  
 La riga di comando SQLMetal illustrata nell'esempio seguente produce Visual Basic codice come modello a oggetti basato su attributi del database di esempio Northwind. Viene eseguito il rendering anche di stored procedure e funzioni.  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>Esempio  
 Usando la riga di comando SQLMetal riportata nell'esempio è possibile produrre codice C# come modello a oggetti basato su attributi del database di esempio Northwind. Viene eseguito il rendering anche di stored procedure e funzioni, mentre i nomi delle tabelle vengono pluralizzati automaticamente.  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)
- [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [Procedura: Personalizzare le classi di entità tramite l'editor di codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Mapping basato su attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
- [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md) (Mapping esterno)
- [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Creazione del modello a oggetti](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
