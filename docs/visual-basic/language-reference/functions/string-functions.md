---
title: Funzioni stringa (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 11ea31ae245d34525ea33d5d2a53a72f1c415b16
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981452"
---
# <a name="string-functions-visual-basic"></a>Funzioni stringa (Visual Basic)
Nella tabella seguente elenca le funzioni disponibili in Visual Basic per cercare e modificare le stringhe.  
  
|Metodo .NET framework|Descrizione|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Restituisce un `Integer` che rappresenta il codice carattere corrispondente a un carattere.|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Restituisce il carattere associato al codice carattere specificato.|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Restituisce una matrice in base zero contenente un subset di un `String` matrice in base ai criteri di filtro specificati.|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Restituisce una stringa formattata in base alle istruzioni contenute in un formato `String` espressione.|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Restituisce un'espressione formattata come un valore di valuta utilizzando il simbolo di valuta definito nel Pannello di controllo del sistema.|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Restituisce un'espressione stringa che rappresenta un valore data/ora.|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Restituisce un'espressione formattata come numero.|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Restituisce un'espressione formattata come percentuale (ovvero moltiplicata per 100) con un carattere % finale.|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Restituisce un integer che specifica la posizione iniziale della prima occorrenza di una stringa in un altro.|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Restituisce la posizione della prima occorrenza di una stringa in un'altra, a partire dalla destra della stringa.|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Restituisce una stringa creata unendo un certo numero di sottostringhe contenute in una matrice.|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Restituisce una stringa o un carattere convertito in caratteri minuscoli.|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Restituisce una stringa contenente un numero specificato di caratteri dal lato sinistro di una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Restituisce un intero che contiene il numero di caratteri in una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Restituisce una stringa allineata a sinistra contenente la stringa specificata adattata alla lunghezza specificata.|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Restituisce una stringa che contiene una copia di una stringa specificata senza spazi iniziali.|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Restituisce una stringa contenente un numero specificato di caratteri da una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Restituisce una stringa in cui una sottostringa specificata è stata sostituita con un'altra sottostringa per un numero di volte specificato.|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Restituisce una stringa contenente un numero specificato di caratteri dal lato destro di una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Restituisce una stringa allineata a destra contenente la stringa specificata adattata alla lunghezza specificata.|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Restituisce una stringa che contiene una copia di una stringa specificata senza spazi finali.|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Restituisce una stringa costituita dal numero specificato di spazi.|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Restituisce una matrice unidimensionale in base zero contenente un numero specificato di sottostringhe.|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Restituisce -1, 0 o 1, in base al risultato di un confronto tra stringhe.|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Restituisce una stringa convertita come specificato.|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Restituisce una stringa o oggetto costituito il carattere specificato ripetuto il numero di volte specificato.|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Restituisce una stringa in cui viene invertito l'ordine dei caratteri di una stringa specificata.|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Restituisce una stringa che contiene una copia di una stringa specificata senza spazi iniziali o finali.|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Restituisce una stringa o un carattere contenente la stringa specificata convertita in caratteri maiuscoli.|  
  
 È possibile usare la [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) consente di eseguire istruzione per specificare se le stringhe vengono confrontate utilizzando un testo tra maiuscole e minuscole ordinamento determinato dalle impostazioni locali del sistema (`Text`) o da rappresentazioni binarie interne del (caratteri `Binary`). Il metodo di confronto del testo predefinito è `Binary`.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene usato il `UCase` funzione per restituire la versione maiuscola di una stringa.  
  
 [!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa la `LTrim` funzione per rimuovere gli spazi iniziali e `RTrim` di spazi di funzione per rimuovere finali da una variabile di stringa. Usa il `Trim` funzione per rimuovere entrambi i tipi degli spazi.  
  
 [!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]  
  
## <a name="example"></a>Esempio  
 Questo esempio viene usato il `Mid` funzione restituisca un numero specificato di caratteri da una stringa.  
  
 [!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa `Len` per restituire il numero di caratteri in una stringa.  
  
 [!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]  
  
## <a name="example"></a>Esempio  
 Questo esempio viene usato il `InStr` funzione per restituire la posizione della prima occorrenza di una stringa in un altro.  
  
 [!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra i vari utilizzi delle `Format` funzione per valori di formato utilizzando sia `String` formati e i formati definiti dall'utente. Per il separatore della data (`/`), il separatore dell'ora (`:`) e gli indicatori AM/PM (`t` e `tt`), l'output formattato visualizzato dal sistema dipende dalle impostazioni locali utilizzate nel codice. Quando tempi e le date vengono visualizzate nell'ambiente di sviluppo, il formato di ora breve e il formato di data breve delle impostazioni locali del codice vengono utilizzati.  
  
> [!NOTE]
>  Per le impostazioni locali che usano un orologio di 24 ore, gli indicatori AM/PM (`t` e `tt`) non visualizzano alcun output.  
  
 [!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Vedere anche
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Membri della libreria di runtime di Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)
- [Riepilogo della modifica delle stringhe](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
