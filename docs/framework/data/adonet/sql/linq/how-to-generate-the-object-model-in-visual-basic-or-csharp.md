---
title: 'Procedura: generare il modello a oggetti in Visual Basic o C#'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ec28b175dddb98eb035061363dd6581e796280b3
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>Procedura: generare il modello a oggetti in Visual Basic o C# #
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping di un modello a oggetti nel linguaggio di programmazione in uso a un database relazionale. Due strumenti sono disponibili per generare automaticamente un [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] modello o c# dai metadati di un database esistente.  
  
-   Se si usa [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], è possibile usare [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per generare un modello a oggetti. Il [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] fornisce un'interfaccia utente avanzata che consente di generare un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modello a oggetti. Per ulteriori informazioni, vedere [Linq to SQL Tools in Visual Studio](https://docs.microsoft.com/en-us/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).
  
-   Lo strumento della riga di comando SQLMetal. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
    > [!NOTE]
    >  Se non si dispone di un database esistente e si desidera crearne uno da un modello a oggetti, è possibile creare il modello a oggetti usando l'editor di codice e <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. Per ulteriori informazioni, vedere [procedura: creazione di un Database in modo dinamico](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).  
  
 Documentazione per il [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] vengono forniti esempi di come generare un [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o modello a oggetti c# usando il [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]. Le informazioni seguenti forniscono esempi relativi all'uso dello strumento della riga di comando SQLMetal. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Esempio  
 Usando la riga di comando SQLMetal riportata nell'esempio è possibile produrre codice [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] come modello a oggetti basato su attributi del database di esempio Northwind. Viene eseguito il rendering anche di stored procedure e funzioni.  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>Esempio  
 Usando la riga di comando SQLMetal riportata nell'esempio è possibile produrre codice C# come modello a oggetti basato su attributi del database di esempio Northwind. Viene eseguito il rendering anche di stored procedure e funzioni, mentre i nomi delle tabelle vengono pluralizzati automaticamente.  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [Procedura: personalizzare classi di entità mediante l'Editor del codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 [Mapping basato su attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md) (Mapping esterno)  
 [Download di database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Creazione del modello a oggetti](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
