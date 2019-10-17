---
title: Funzioni stringa (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 32a31a881573cc9dc481fc07fc4067569a96a963
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395830"
---
# <a name="string-functions-visual-basic"></a>Funzioni stringa (Visual Basic)

Nella tabella seguente sono elencate le funzioni fornite da Visual Basic nella classe <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> per la ricerca e la modifica delle stringhe. Possono essere considerati come Visual Basic funzioni intrinseche; ovvero non è necessario chiamarli come membri espliciti di una classe, come illustrato negli esempi. Altri metodi e in alcuni casi metodi complementari sono disponibili nella classe <xref:System.String?displayProperty=nameWithType>. 
  
|Metodo .NET Framework|Descrizione|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Restituisce un valore `Integer` che rappresenta il codice carattere corrispondente a un carattere.|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Restituisce il carattere associato al codice carattere specificato.|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Restituisce una matrice in base zero contenente un subset di una matrice `String` in base ai criteri di filtro specificati.|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Restituisce una stringa formattata in base alle istruzioni contenute in un formato @no__t espressione-0.|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Restituisce un'espressione formattata come valore di valuta utilizzando il simbolo di valuta definito nel pannello di controllo del sistema.|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Restituisce un'espressione stringa che rappresenta un valore di data/ora.|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Restituisce un'espressione formattata come numero.|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Restituisce un'espressione formattata come percentuale (ovvero moltiplicata per 100) con un carattere % finale.|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Restituisce un Integer che specifica la posizione iniziale della prima occorrenza di una stringa all'interno di un altro.|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Restituisce la posizione della prima occorrenza di una stringa all'interno di un'altra, a partire dal lato destro della stringa.|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Restituisce una stringa creata mediante l'Unione di un numero di sottostringhe contenute in una matrice.|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Restituisce una stringa o un carattere convertito in caratteri minuscoli.|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Restituisce una stringa contenente un numero specificato di caratteri dal lato sinistro di una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Restituisce un intero contenente il numero di caratteri in una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Restituisce una stringa allineata a sinistra contenente la stringa specificata adattata alla lunghezza specificata.|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Restituisce una stringa contenente una copia di una stringa specificata senza spazi iniziali.|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Restituisce una stringa contenente un numero specificato di caratteri da una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Restituisce una stringa in cui una sottostringa specificata è stata sostituita con un'altra sottostringa per un numero specificato di volte.|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Restituisce una stringa contenente un numero specificato di caratteri dal lato destro di una stringa.|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Restituisce una stringa allineata a destra contenente la stringa specificata adattata alla lunghezza specificata.|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Restituisce una stringa contenente una copia di una stringa specificata senza spazi finali.|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Restituisce una stringa costituita dal numero di spazi specificato.|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Restituisce una matrice unidimensionale in base zero contenente un numero specificato di sottostringhe.|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Restituisce-1, 0 o 1, in base al risultato di un confronto tra stringhe.|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Restituisce una stringa convertita come specificato.|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Restituisce una stringa o un oggetto costituito dal carattere specificato ripetuto per il numero di volte specificato.|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Restituisce una stringa in cui l'ordine dei caratteri di una stringa specificata è invertito.|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Restituisce una stringa contenente una copia di una stringa specificata senza spazi iniziali o finali.|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Restituisce una stringa o un carattere contenente la stringa specificata convertita in caratteri maiuscoli.|  
  
 È possibile usare l'istruzione [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) per impostare se le stringhe vengono confrontate usando un ordinamento del testo senza distinzione tra maiuscole e minuscole determinato dalle impostazioni locali del sistema (`Text`) o dalle rappresentazioni binarie interne dei caratteri (`Binary`). Il metodo di confronto del testo predefinito è `Binary`.  
  
## <a name="example-ucase"></a>Esempio: UCase

In questo esempio viene utilizzata la funzione `UCase` per restituire una versione in maiuscolo di una stringa.  
[!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]  
  
## <a name="example-ltrim"></a>Esempio: LTrim

In questo esempio viene utilizzata la funzione `LTrim` per rimuovere gli spazi iniziali e la funzione `RTrim` per rimuovere gli spazi finali da una variabile di stringa. Usa la funzione `Trim` per rimuovere entrambi i tipi di spazi.  
  
[!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]  
  
## <a name="example-mid"></a>Esempio: Mid

In questo esempio viene utilizzata la funzione `Mid` per restituire un numero specificato di caratteri da una stringa.  

[!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]  

## <a name="example-len"></a>Esempio: Len

In questo esempio viene utilizzato `Len` per restituire il numero di caratteri in una stringa.  
  
[!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]  
  
## <a name="example-instr"></a>Esempio: InStr

In questo esempio viene utilizzata la funzione `InStr` per restituire la posizione della prima occorrenza di una stringa all'interno di un'altra.  
  
[!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]  
  
## <a name="example-format"></a>Esempio: Format

Questo esempio mostra diversi usi della funzione `Format` per formattare i valori usando formati `String` e formati definiti dall'utente. Per il separatore della data (`/`), il separatore dell'ora (`:`) e gli indicatori AM/PM (`t` e `tt`), l'output formattato effettivo visualizzato dal sistema dipende dalle impostazioni locali utilizzate dal codice. Quando le ore e le date vengono visualizzate nell'ambiente di sviluppo, vengono utilizzati il formato di ora breve e il formato di data breve delle impostazioni locali del codice.  
  
> [!NOTE]
> Per le impostazioni locali che utilizzano un orario a 24 ore, gli indicatori AM/PM (`t` e `tt`) non visualizzano alcun valore.  
  
 [!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Vedere anche

- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Membri della libreria di runtime di Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)
- [Riepilogo della modifica delle stringhe](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
- [Metodi della classe System. String](xref:System.String#methods)
