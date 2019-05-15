---
title: Introduzione a LINQ (C#)
ms.date: 07/20/2015
ms.assetid: 54874feb-55e5-4ca8-a9d6-1c1127fd7fb1
ms.openlocfilehash: b8a577c7f1cb89df5534ae0eca893f4db434301e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596581"
---
# <a name="introduction-to-linq-c"></a>Introduzione a LINQ (C#)
LINQ (Language-Integrated Query) rappresenta una novità introdotta in .NET Framework versione 3.5 che colma il divario tra il mondo degli oggetti e il mondo dei dati.  
  
 In genere, le query sui dati vengono espresse come stringhe semplici senza il controllo dei tipi in fase di compilazione o il supporto di IntelliSense. È anche necessario apprendere un linguaggio di query diverso per ogni tipo di origine dati: database SQL, documenti XML, vari servizi Web e così via. LINQ rende una *query* un costrutto di linguaggio di prima categoria in C#. È possibile scrivere query su insiemi di oggetti fortemente tipizzati usando le parole chiave del linguaggio e gli operatori comuni.  
  
 È possibile scrivere query LINQ in C# per database SQL Server, documenti XML, set di dati ADO.NET e qualsiasi raccolta di oggetti che supporta <xref:System.Collections.IEnumerable> o l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> generica. Il supporto per LINQ viene anche offerto da terze parti per numerosi servizi Web e altre implementazioni di database.  
  
 È possibile usare le query LINQ nei nuovi progetti o insieme alle query non LINQ nei progetti esistenti. L'unico requisito è che il progetto sia destinato a .NET Framework 3.5 o versione successiva.  
  
 Nella figura seguente presa da Visual Studio viene illustrata una query LINQ completata parzialmente su un database di SQL Server in C# e Visual Basic con controllo completo del tipo e supporto IntelliSense:  
  
 ![Diagramma che illustra una query LINQ con Intellisense.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a>Passaggi successivi  
 Per altre informazioni dettagliate su LINQ, iniziare ad acquisire dimestichezza con alcuni concetti di base nella sezione introduttiva [Introduzione all'uso di LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) e quindi leggere la documentazione per la tecnologia LINQ a cui si è interessati:  
  
- Database SQL Server: [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
  
- Documenti XML: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)  
  
- Set di dati ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
- Raccolte, file e stringhe .NET e così via: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a>Vedere anche

- [Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
