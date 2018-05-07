---
title: Analisi del codice sorgente in LINQ to SQL
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: 25c54fa67171b456b2eeb5c30f52d1e654fca995
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="analyzing-linq-to-sql-source-code"></a>Analisi del codice sorgente in LINQ to SQL
Usando i passaggi seguenti, è possibile produrre codice sorgente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dal database di esempio Northwind. Gli elementi del modello a oggetti possono essere confrontati con gli elementi del database per verificare come viene eseguito il mapping dei diversi elementi.  
  
> [!NOTE]
>  Gli sviluppatori che usano Visual Studio è possono utilizzare il [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] per produrre il codice.  
  
1.  Se nel computer di sviluppo non è già disponibile il database di esempio Northwind, è possibile scaricarlo gratuitamente. Per ulteriori informazioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  
  
2.  Usare lo strumento della riga di comando SqlMetal per generare un file di origine di Visual Basic o C#. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md). Digitando i comandi seguenti al prompt dei comandi, è possibile generare file di origine di Visual Basic e C# contenenti stored procedure e funzioni:  
  
    -   `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    -   `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
