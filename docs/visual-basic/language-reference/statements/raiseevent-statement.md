---
title: Istruzione RaiseEvent
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: e04f2bbaf57789f0bdaa07c1ebd68b22e3ae6178
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333052"
---
# <a name="raiseevent-statement"></a>Istruzione RaiseEvent
Attiva un evento dichiarato a livello di modulo all'interno di una classe, un form o un documento.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>Parti  
 `eventname`  
 Obbligatoria. Nome dell'evento da attivare.  
  
 `argumentlist`  
 Facoltativa. Elenco delimitato da virgole di variabili, matrici o espressioni. Il `argumentlist` argomento deve essere racchiuso tra parentesi. Se non è presente alcun argomento, le parentesi devono essere omesse.  
  
## <a name="remarks"></a>Note  
 Il `eventname` obbligatorio è il nome di un evento dichiarato all'interno del modulo. Segue Visual Basic convenzioni di denominazione delle variabili.  
  
 Se l'evento non è stato dichiarato all'interno del modulo in cui viene generato, si verifica un errore. Nel frammento di codice seguente viene illustrata una dichiarazione di evento e una procedura in cui viene generato l'evento.  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 Non è possibile usare `RaiseEvent` per generare eventi non dichiarati in modo esplicito nel modulo. Ad esempio, tutti i form ereditano un evento <xref:System.Windows.Forms.Control.Click> da <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, non possono essere generati utilizzando `RaiseEvent` in un formato derivato. Se si dichiara un evento `Click` nel modulo modulo, viene ombreggiato il <xref:System.Windows.Forms.Control.Click> evento del modulo. È comunque possibile richiamare l'evento <xref:System.Windows.Forms.Control.Click> del form chiamando il metodo <xref:System.Windows.Forms.Control.OnClick%2A>.  
  
 Per impostazione predefinita, un evento definito in Visual Basic genera i relativi gestori eventi nell'ordine in cui vengono stabilite le connessioni. Poiché gli eventi possono avere parametri `ByRef`, un processo che si connette in ritardo può ricevere parametri che sono stati modificati da un gestore eventi precedente. Dopo l'esecuzione dei gestori di eventi, il controllo viene restituito alla subroutine che ha generato l'evento.  
  
> [!NOTE]
> Gli eventi non condivisi non devono essere generati all'interno del costruttore della classe in cui sono dichiarati. Sebbene tali eventi non causino errori in fase di esecuzione, potrebbero non essere rilevati dai gestori eventi associati. Usare il modificatore `Shared` per creare un evento condiviso se è necessario generare un evento da un costruttore.  
  
> [!NOTE]
> È possibile modificare il comportamento predefinito degli eventi definendo un evento personalizzato. Per gli eventi personalizzati, l'istruzione `RaiseEvent` richiama la funzione di accesso `RaiseEvent` dell'evento. Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti, gli eventi vengono usati per il conto alla rovescia dei secondi, da 10 a 0. Nel codice vengono illustrati diversi metodi, proprietà e istruzioni correlati agli eventi, inclusa l'istruzione `RaiseEvent`.  
  
 La classe che genera un evento viene definita origine e i metodi che lo elaborano vengono definiti gestori eventi. Un'origine eventi può disporre di più gestori per gli eventi generati. Quando la classe genera l'evento, lo stesso evento viene generato in tutte le classi per cui è stato scelto di gestire eventi per tale istanza dell'oggetto.  
  
 Nell'esempio vengono usati anche un form (`Form1`) con un pulsante (`Button1`) e una casella di testo (`TextBox1`). Quando si fa clic sul pulsante, nella prima casella di testo viene visualizzato il conto alla rovescia dei secondi da 10 a 0. Al termine dei 10 secondi, nella prima casella di testo viene visualizzato "Done".  
  
 Il codice di `Form1` specifica gli stati di inizio e fine del form. Contiene inoltre il codice eseguito quando vengono generati gli eventi.  
  
 Per usare questo esempio, aprire un nuovo progetto di applicazione Windows, aggiungere un pulsante denominato `Button1` e una casella di testo denominata `TextBox1` al form principale, denominato `Form1`. Fare quindi clic con il pulsante destro del mouse sul form e scegliere **Visualizza codice** per aprire l'editor di codice.  
  
 Aggiungere una variabile di `WithEvents` alla sezione delle dichiarazioni della classe `Form1`.  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a>Esempio  
 Aggiungere il codice seguente al codice per `Form1`: Sostituire eventuali procedure duplicate che possono esistere, ad esempio `Form_Load`o `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 Premere F5 per eseguire l'esempio precedente e fare clic sul pulsante **Avvia**. Nella prima casella di testo viene avviato il conto alla rovescia dei secondi. Al termine dei 10 secondi, nella prima casella di testo viene visualizzato "Done".  
  
> [!NOTE]
> Il metodo `My.Application.DoEvents` non elabora gli eventi esattamente allo stesso modo del modulo. Per consentire al modulo di gestire direttamente gli eventi, è possibile utilizzare il multithreading. Per altre informazioni, vedere [Threading gestito](../../../standard/threading/index.md).  
  
## <a name="see-also"></a>Vedere anche

- [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Istruzione AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [Istruzione RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
