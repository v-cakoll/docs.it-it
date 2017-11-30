---
title: Funzioni stringa (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7672f03cda99aa0e1dcecd79b0358f9d5f16f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="string-functions-visual-basic"></a>Funzioni stringa (Visual Basic)
Nella tabella seguente sono elencate le funzioni disponibili in Visual Basic per la ricerca e modificare le stringhe.  
  
|Metodo .NET framework|Descrizione|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Restituisce un `Integer` che rappresenta il codice carattere corrispondente a un carattere.|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Restituisce il carattere associato al codice di carattere specificato.|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Restituisce una matrice in base zero contenente un subset di un `String` matrice in base ai criteri di filtro specificati.|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Restituisce una stringa formattata in base alle istruzioni contenute in un formato `String` espressione.|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Restituisce un'espressione formattata come un valore di valuta utilizzando il simbolo di valuta definito nel Pannello di controllo del sistema.|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Restituisce un'espressione stringa che rappresenta un valore data/ora.|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Restituisce un'espressione formattata come un numero.|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Restituisce un'espressione formattata come percentuale (ovvero moltiplicata per 100) con un carattere % finale.|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Restituisce un intero che specifica la posizione iniziale della prima occorrenza di una stringa all'interno di altra.|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Restituisce la posizione della prima occorrenza di una stringa all'interno di un'altra, a partire dal lato destro della stringa.|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Restituisce una stringa creata unendo in join un numero di sottostringhe contenute in una matrice.|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Restituisce una stringa o un carattere convertito in caratteri minuscoli.|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Restituisce una stringa contenente un numero specificato di caratteri dal lato sinistro di una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Restituisce un intero che contiene il numero di caratteri in una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Restituisce una stringa allineata a sinistra contenente la stringa specificata adattata alla lunghezza specificata.|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Restituisce una stringa contenente una copia di una stringa specificata senza spazi iniziali.|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Restituisce una stringa contenente un numero specificato di caratteri da una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Restituisce una stringa in cui una sottostringa specificata è stata sostituita con un'altra sottostringa per il numero di volte.|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Restituisce una stringa contenente un numero specificato di caratteri dal lato destro di una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Restituisce una stringa allineata a destra contenente la stringa specificata adattata alla lunghezza specificata.|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Restituisce una stringa contenente una copia di una stringa specificata senza spazi finali.|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Restituisce una stringa costituita dal numero specificato di spazi.|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Restituisce una matrice unidimensionale in base zero contenente un numero specificato di sottostringhe.|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Restituisce -1, 0 o 1, in base al risultato di un confronto tra stringhe.|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Restituisce una stringa convertita nel modo specificato.|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Restituisce una stringa o oggetto costituito dal carattere specificato ripetuto il numero di volte specificato.|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Restituisce una stringa in cui viene invertito l'ordine dei caratteri di una stringa specificata.|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Restituisce una stringa contenente una copia di una stringa specificata senza spazi iniziali o finali.|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Restituisce una stringa o carattere contenente la stringa specificata convertita in caratteri maiuscoli.|  
  
 È possibile utilizzare il [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) istruzione per specificare se le stringhe vengono confrontate con una distinzione tra maiuscole ordinamento determinato dalle impostazioni locali del sistema (`Text`) o da rappresentazioni binarie interne del (caratteri `Binary`). Il metodo di confronto del testo predefinito è `Binary`.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `UCase` funzione per restituire la versione maiuscola di una stringa.  
  
 [!code-vb[VbVbalrStrings#31](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_1.vb)]  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `LTrim` funzione per rimuovere gli spazi iniziali e `RTrim` di spazi di funzione per rimuovere finali da una variabile di stringa. Usa il `Trim` funzione per rimuovere entrambi i tipi di spazi.  
  
 [!code-vb[VbVbalrStrings#25](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_2.vb)]  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `Mid` funzione per restituire un numero specificato di caratteri da una stringa.  
  
 [!code-vb[VbVbalrStrings#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_3.vb)]  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato `Len` per restituire il numero di caratteri in una stringa.  
  
 [!code-vb[VbVbalrStrings#33](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_4.vb)]  
  
## <a name="example"></a>Esempio  
 Questo esempio viene utilizzato il `InStr` funzione per restituire la posizione della prima occorrenza di una stringa all'interno di altra.  
  
 [!code-vb[VbVbalrStrings#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_5.vb)]  
  
## <a name="example"></a>Esempio  
 Questo esempio mostra vari usi del `Format` funzione a valori di formato utilizzando sia `String` formati e i formati definiti dall'utente. Per il separatore della data (`/`), il separatore dell'ora (`:`) e gli indicatori AM/PM (`t` e `tt`), l'output formattato visualizzato dal sistema dipende dalle impostazioni locali utilizzate nel codice. Quando tempi e le date vengono visualizzate nell'ambiente di sviluppo, il formato di ora breve e il formato di data breve delle impostazioni locali del codice vengono utilizzati.  
  
> [!NOTE]
>  Per le impostazioni locali che utilizzano un orologio di 24 ore, gli indicatori AM/PM (`t` e `tt`) non visualizzano alcun output.  
  
 [!code-vb[VbVbalrStrings#27](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_6.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)  
 [Membri della libreria di runtime di Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)  
 [Riepilogo della modifica delle stringhe](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
