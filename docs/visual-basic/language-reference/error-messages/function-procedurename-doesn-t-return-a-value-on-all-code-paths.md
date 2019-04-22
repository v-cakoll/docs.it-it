---
title: La funzione '<procedurename>' non restituisce un valore in tutti i percorsi del codice
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: badcfea4f24ba3858071e02ba47b8f77ab557f88
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824832"
---
# <a name="function-procedurename-doesnt-return-a-value-on-all-code-paths"></a>Funzione '\<nomeroutine >' non restituisce un valore per tutti i percorsi del codice
Funzione '\<nomeroutine >' non restituisce un valore per tutti i percorsi del codice. Probabilmente manca un'istruzione 'Return'.  
  
 Oggetto `Function` procedure dispone di almeno un possibile percorso all'interno del codice che non restituisce un valore.  
  
 È possibile restituire un valore da un `Function` procedure in uno dei modi seguenti:  
  
-   Includere il valore in una [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Assegnare il valore per il `Function` procedure assegnare un nome e quindi eseguire un `Exit Function` istruzione.  
  
-   Assegnare il valore per il `Function` procedure assegnare un nome e quindi eseguire il `End Function` istruzione.  
  
 Se il controllo passa al `Exit Function` o `End Function` e non è stato assegnato alcun valore per il nome della routine, la procedura restituisce il valore predefinito del tipo di dati restituito. Per altre informazioni, vedere "Comportamento di" nella [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42105  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Controllare la logica del flusso di controllo e assicurarsi che si assegna un valore prima di ogni istruzione che provoca un valore restituito.  
  
     È più semplice garantire che ogni restituito dalla routine restituisce un valore se si usano sempre il `Return` istruzione. Se si esegue questa operazione, l'ultima istruzione che precede `End Function` deve essere un `Return` istruzione.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Function](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)
- [Pagina Compilazione, Creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
