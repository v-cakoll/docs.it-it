---
title: 'Procedura: Generare codice personalizzato modificando un file DBML'
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: 01890e6b899db6b70049e2d6b8193e5b0f4095fb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781974"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Procedura: Generare codice personalizzato modificando un file DBML
È possibile generare Visual Basic o C# codice sorgente da un file di metadati con estensione dbml (database Markup Language). Questo approccio consente di personalizzare il file DBML predefinito prima di generare il codice di mapping dell'applicazione. Si tratta di una funzionalità avanzata.  
  
 Di seguito sono elencati i passaggi di questo processo.  
  
1. Generare un file con estensione dbml.  
  
2. Usare un editor per modificare il file con estensione dbml, Si noti che il file. dbml deve essere convalidato in base al file di definizione [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dello schema (con estensione XSD) per i file con estensione dbml. Per altre informazioni, vedere [generazione di codice in LINQ to SQL](code-generation-in-linq-to-sql.md).  
  
3. Generare il Visual Basic o C# il codice sorgente.  
  
 Negli esempi seguenti viene usato lo strumento della riga di comando SQLMetal. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene generato un file con estensione dbml dal database di esempio Northwind. Come origine per i metadati del database è possibile usare il nome del database o il nome del file con estensione mdf.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Esempio  
 Il codice seguente genera Visual Basic o C# un file di codice sorgente da un file con estensione dbml.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>Vedere anche

- [Generazione di codice in LINQ to SQL](code-generation-in-linq-to-sql.md)
- [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [Creazione del modello a oggetti](creating-the-object-model.md)
