---
title: Proprietà &#39; &lt;propertyname&gt; &#39; &#39;t restituisce un valore in tutti i percorsi del codice
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 72bc7e45cadd2528f29c88bf6e80ee5f381052dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594214"
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Proprietà &#39; &lt;propertyname&gt; &#39; &#39;t restituisce un valore in tutti i percorsi del codice
Proprietà '\<NomeProprietà >' non restituisce un valore per tutti i percorsi di codice. In fase di esecuzione, quando viene usato il risultato, potrebbe verificarsi un'eccezione dovuta a un riferimento Null.  
  
 Una proprietà `Get` procedura contiene almeno un possibile percorso all'interno del codice che non restituisce un valore.  
  
 È possibile restituire un valore da una proprietà `Get` procedura in uno dei modi seguenti:  
  
-   Assegnare il valore per il nome della proprietà, quindi eseguire un `Exit Property` istruzione.  
  
-   Assegnare il valore per il nome della proprietà, quindi eseguire il `End Get` istruzione.  
  
-   Includere il valore in un [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Se il controllo passa al `Exit Property` o `End Get` e non, è stato assegnato alcun valore per il nome della proprietà di `Get` procedura restituisce il valore predefinito del tipo di dati della proprietà. Per ulteriori informazioni, vedere "Comportamento" in [istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42107  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Controllare la logica del flusso di controllo e assicurarsi di assegnare un valore prima di ogni istruzione che causa la restituzione.  
  
     È più semplice garantire che ogni restituito dalla routine restituisce un valore se si utilizza sempre il `Return` istruzione. In questo caso, l'ultima istruzione prima `End Get` deve essere un `Return` istruzione.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine Property](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Istruzione Get](../../../visual-basic/language-reference/statements/get-statement.md)
