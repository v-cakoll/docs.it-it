---
title: "Espressione di tipo &lt;tipo&gt; non è disponibile per query"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3f2b98bf48f0b3965929f9211c2944ff97754f23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a>Espressione di tipo &lt;tipo&gt; non è disponibile per query
Espressione di tipo \<tipo > non è disponibile per query. Assicurarsi che non manchi un'importazione di riferimento e/o dello spazio dei nomi di assembly per il provider LINQ.  
  
 Tipi di query sono definiti nel <xref:System.Linq>, <xref:System.Data.Linq>, e <xref:System.Xml.Linq> gli spazi dei nomi. È necessario importare uno o più di questi spazi dei nomi per eseguire query LINQ.  
  
 Il <xref:System.Linq> spazio dei nomi consente agli oggetti di query, ad esempio raccolte e matrici utilizzando LINQ.  
  
 Il <xref:System.Data.Linq> spazio dei nomi consente di eseguire una query di set di dati ADO.NET e database di SQL Server utilizzando LINQ.  
  
 Il <xref:System.Xml.Linq> dello spazio dei nomi consente di eseguire query XML utilizzando LINQ e di utilizzare funzionalità XML in Visual Basic.  
  
 **ID errore:** BC36593  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Aggiungere un `Import` istruzione per il <xref:System.Linq>, <xref:System.Data.Linq>, o <xref:System.Xml.Linq> dello spazio dei nomi al file di codice. È inoltre possibile importare gli spazi dei nomi per il progetto utilizzando il **riferimenti** pagina della finestra di Progettazione progetti (**progetto**).  
  
2.  Verificare che il tipo che è stato identificato come origine della query è un tipo queryable. Ovvero, un tipo che implementa <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Linq>  
 <xref:System.Data.Linq>  
 <xref:System.Xml.Linq>  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Riferimenti e istruzione Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Pagina Riferimenti, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
