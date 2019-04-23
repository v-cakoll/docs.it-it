---
title: L'espressione di tipo <type> non può essere sottoposta a query
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 121c0a95a3a6bb695d9c73347c733cba215a0de4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304155"
---
# <a name="expression-of-type-type-is-not-queryable"></a>Espressione di tipo \<tipo > non è disponibile per query
Espressione di tipo \<tipo > non è disponibile per query. Assicurarsi che sia presente un'importazione di riferimento e/o lo spazio dei nomi di assembly per il provider LINQ.  
  
 Tipi queryable sono definiti nel <xref:System.Linq>, <xref:System.Data.Linq>, e <xref:System.Xml.Linq> gli spazi dei nomi. È necessario importare uno o più di questi spazi dei nomi per eseguire query LINQ.  
  
 Il <xref:System.Linq> spazio dei nomi consente agli oggetti di query, ad esempio le raccolte e matrici usando LINQ.  
  
 Il <xref:System.Data.Linq> dello spazio dei nomi consente di eseguire query sui set di dati ADO.NET e i database di SQL Server usando LINQ.  
  
 Il <xref:System.Xml.Linq> dello spazio dei nomi consente di eseguire query XML con LINQ e usare le funzionalità XML in Visual Basic.  
  
 **ID errore:** BC36593  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Aggiungere un `Import` istruzione per il <xref:System.Linq>, <xref:System.Data.Linq>, o <xref:System.Xml.Linq> dello spazio dei nomi al file di codice. È anche possibile importare gli spazi dei nomi per il progetto utilizzando il **riferimenti** pagina della finestra di Progettazione progetti (**My Project**).  
  
2. Verificare che il tipo identificato come origine della query è un tipo queryable. Vale a dire, un tipo che implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Riferimenti e istruzione Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Pagina Riferimenti, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
