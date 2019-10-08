---
title: 'Procedura: Generare il modello a oggetti in Visual Basic o C#'
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 7d2c0600534c93f5884eec48a4bdaa3ce99945e9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002811"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>Procedura: Generare il modello a oggetti in Visual Basic o C @ no__t-0
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping di un modello a oggetti nel linguaggio di programmazione in uso a un database relazionale. Sono disponibili due strumenti per la generazione automatica di un C# Visual Basic o di un modello dai metadati di un database esistente.  
  
- Se si utilizza Visual Studio, è possibile utilizzare il Object Relational Designer per generare un modello a oggetti. In Progettazione relazionale oggetti è disponibile un'interfaccia utente avanzata che consente di generare un modello a oggetti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Per altre informazioni, vedere [strumenti LINQ to SQL in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).
  
- Lo strumento della riga di comando SQLMetal. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
    > [!NOTE]
    > Se non si dispone di un database esistente e si desidera crearne uno da un modello a oggetti, è possibile creare il modello a oggetti usando l'editor di codice e <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. Per altre informazioni, vedere [Procedura: Creare un database in modo dinamico @ no__t-0.  
  
 La documentazione relativa a Progettazione relazionale oggetti fornisce esempi su come generare un modello a C# oggetti o Visual Basic usando la finestra di progettazione di o/r. Le informazioni seguenti forniscono esempi relativi all'uso dello strumento della riga di comando SQLMetal. Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Esempio  
 La riga di comando SQLMetal illustrata nell'esempio seguente produce Visual Basic codice come modello a oggetti basato su attributi del database di esempio Northwind. Viene eseguito il rendering anche di stored procedure e funzioni.  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>Esempio  
 Usando la riga di comando SQLMetal riportata nell'esempio è possibile produrre codice C# come modello a oggetti basato su attributi del database di esempio Northwind. Viene eseguito il rendering anche di stored procedure e funzioni, mentre i nomi delle tabelle vengono pluralizzati automaticamente.  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori](programming-guide.md)
- [Modello a oggetti LINQ to SQL](the-linq-to-sql-object-model.md)
- [Apprendimento tramite procedure dettagliate](learning-by-walkthroughs.md)
- [Procedura: Personalizzare le classi di entità tramite l'editor di codice @ no__t-0
- [Mapping basato su attributi](attribute-based-mapping.md)
- [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [External Mapping](external-mapping.md) (Mapping esterno)
- [Download di database di esempio](downloading-sample-databases.md)
- [Creazione del modello a oggetti](creating-the-object-model.md)
