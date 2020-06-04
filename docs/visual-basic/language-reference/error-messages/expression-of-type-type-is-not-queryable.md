---
title: L'espressione di tipo <type> non può essere sottoposta a query
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: e61b4dac109f714b5cf25226d1029237ca77032d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409478"
---
# <a name="expression-of-type-type-is-not-queryable"></a>L'espressione di tipo \<type> non può essere sottoposta a query
L'espressione di tipo \<type> non è Queryable. Verificare che non manchi un riferimento all'assembly e/o l'importazione dello spazio dei nomi per il provider LINQ.  
  
 I tipi queryable sono definiti negli <xref:System.Linq> <xref:System.Data.Linq> <xref:System.Xml.Linq> spazi dei nomi, e. Per eseguire query LINQ è necessario importare uno o più di questi spazi dei nomi.  
  
 Lo <xref:System.Linq> spazio dei nomi consente di eseguire query su oggetti quali raccolte e matrici utilizzando LINQ.  
  
 Lo <xref:System.Data.Linq> spazio dei nomi consente di eseguire query sui set di dati ADO.NET e SQL Server database usando LINQ.  
  
 Lo <xref:System.Xml.Linq> spazio dei nomi consente di eseguire query su XML utilizzando LINQ e di utilizzare le funzionalità XML in Visual Basic.  
  
 **ID errore:** BC36593  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Aggiungere un' `Import` istruzione per lo <xref:System.Linq> <xref:System.Data.Linq> <xref:System.Xml.Linq> spazio dei nomi, o al file di codice. È anche possibile importare gli spazi dei nomi per il progetto tramite la pagina **riferimenti** di progettazione progetti (**progetto**).  
  
2. Verificare che il tipo identificato come origine della query sia un tipo Queryable. Ovvero un tipo che implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../programming-guide/language-features/linq/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
- [Riferimenti e istruzione Imports](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../statements/imports-statement-net-namespace-and-type.md)
- [Riferimenti (pagina), Creazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
