---
title: Funzione &#39; &lt;nomeroutine&gt;&#39; &#39; t restituisce un valore in tutti i percorsi del codice
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords: BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5244d97a79f2450f44fe05f63510369914375912
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Funzione &#39; &lt;nomeroutine&gt;&#39; &#39; t restituisce un valore in tutti i percorsi del codice
Funzione '\<nomeroutine >' non restituisce un valore per tutti i percorsi di codice. Probabilmente manca un'istruzione 'Return'.  
  
 Oggetto `Function` procedura contiene almeno un possibile percorso all'interno del codice che non restituisce un valore.  
  
 È possibile restituire un valore da un `Function` procedura in uno dei modi seguenti:  
  
-   Includere il valore in un [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Assegnare il valore per il `Function` procedure un nome e quindi eseguire un `Exit Function` istruzione.  
  
-   Assegnare il valore per il `Function` procedure un nome e quindi eseguire il `End Function` istruzione.  
  
 Se il controllo passa al `Exit Function` o `End Function` e non, è stato assegnato alcun valore per il nome della stored procedure, la procedura restituisce il valore predefinito del tipo di dati restituito. Per ulteriori informazioni, vedere "Comportamento" in [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42105  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Controllare la logica del flusso di controllo e assicurarsi di assegnare un valore prima di ogni istruzione che causa la restituzione.  
  
     È più semplice garantire che ogni restituito dalla routine restituisce un valore se si utilizza sempre il `Return` istruzione. In questo caso, l'ultima istruzione prima `End Function` deve essere un `Return` istruzione.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Pagina Compilazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
