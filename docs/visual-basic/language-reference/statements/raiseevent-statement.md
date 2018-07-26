---
title: Istruzione RaiseEvent (Visual Basic)
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
ms.openlocfilehash: ef4dce290a7a7f6340b15aa4083cd40518e37d0d
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245217"
---
# <a name="raiseevent-statement"></a>Istruzione RaiseEvent
Attiva un evento dichiarato a livello di modulo all'interno di una classe, modulo o documento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>Parti  
 `eventname`  
 Obbligatorio. Nome dell'evento da attivare.  
  
 `argumentlist`  
 Facoltativo. Elenco delimitato da virgole di variabili, matrici o le espressioni. Il `argumentlist` argomento deve essere racchiuso tra parentesi. Se non sono presenti argomenti, le parentesi devono essere omessa.  
  
## <a name="remarks"></a>Note  
 Obbligatorio `eventname` è il nome di un evento dichiarato all'interno del modulo. Segue le convenzioni di denominazione variabile Visual Basic.  
  
 Se l'evento non è stata dichiarata all'interno del modulo in cui viene generato, si verifica un errore. Il frammento di codice seguente viene illustrata una dichiarazione di evento e una procedura in cui viene generato l'evento.  
  
 [!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]  
  
 Non è possibile usare `RaiseEvent` per generare eventi che non sono esplicitamente dichiarati nel modulo. Ad esempio, tutti i form ereditano un <xref:System.Windows.Forms.Control.Click> evento dal <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, non può essere generato mediante `RaiseEvent` in un form derivato. Se si dichiara un `Click` evento nel modulo del form, nasconde il modulo <xref:System.Windows.Forms.Control.Click> evento. È comunque possibile richiamare il modulo <xref:System.Windows.Forms.Control.Click> evento chiamando il <xref:System.Windows.Forms.Control.OnClick%2A> (metodo).  
  
 Per impostazione predefinita, un evento definito in Visual Basic genera relativi gestori di eventi nell'ordine che le connessioni vengono stabilite. Poiché gli eventi possono essere `ByRef` parametri, i parametri che sono stati modificati da un gestore dell'evento precedente è che venga visualizzato un processo che si connette più tardi. Dopo l'esecuzione i gestori eventi, il controllo viene restituito alla subroutine che ha generato l'evento.  
  
> [!NOTE]
>  Gli eventi non condivisi non dovrebbero essere generati all'interno del costruttore della classe in cui sono dichiarate. Anche se tali eventi non causano errori di run-time, è possibile che non vengano rilevati dai gestori eventi associati. Usare il `Shared` modificatore per creare un evento condiviso se si desidera generare un evento da un costruttore.  
  
> [!NOTE]
>  È possibile modificare il comportamento predefinito degli eventi mediante la definizione di un evento personalizzato. Per gli eventi personalizzati, il `RaiseEvent` istruzione richiama l'evento `RaiseEvent` della funzione di accesso. Per altre informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Esempio  
 Negli esempi seguenti, gli eventi vengono usati per il conto alla rovescia dei secondi, da 10 a 0. Il codice illustra numerosi i metodi correlati agli eventi, proprietà e le istruzioni, inclusa la `RaiseEvent` istruzione.  
  
 La classe che genera un evento viene definita origine e i metodi che lo elaborano vengono definiti gestori eventi. Un'origine eventi può disporre di più gestori per gli eventi generati. Quando la classe genera l'evento, lo stesso evento viene generato in tutte le classi per cui è stato scelto di gestire eventi per tale istanza dell'oggetto.  
  
 Nell'esempio vengono usati anche un form (`Form1`) con un pulsante (`Button1`) e una casella di testo (`TextBox1`). Quando si fa clic sul pulsante, nella prima casella di testo viene visualizzato il conto alla rovescia dei secondi da 10 a 0. Al termine dei 10 secondi, nella prima casella di testo viene visualizzato "Done".  
  
 Il codice di `Form1` specifica gli stati di inizio e fine del form. Contiene inoltre il codice eseguito quando vengono generati gli eventi.  
  
 Per usare questo esempio, aprire un nuovo progetto applicazione Windows, aggiungere un pulsante denominato `Button1` e una casella di testo denominato `TextBox1` al form principale, denominato `Form1`. Quindi fare clic sul form e fare clic su **Visualizza codice** per aprire l'Editor di codice.  
  
 Aggiungere un `WithEvents` alla sezione delle dichiarazioni di variabili di `Form1` classe.  
  
 [!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]  
  
## <a name="example"></a>Esempio  
 Aggiungere il codice seguente al codice per `Form1`: Sostituire eventuali routine duplicate che potrebbero esistere, ad esempio `Form_Load`, o `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]  
  
 Premere F5 per eseguire l'esempio precedente, quindi fare clic sul pulsante con etichettato **avviare**. Nella prima casella di testo viene avviato il conto alla rovescia dei secondi. Al termine dei 10 secondi, nella prima casella di testo viene visualizzato "Done".  
  
> [!NOTE]
>  Il `My.Application.DoEvents` metodo non elabora gli eventi in esattamente allo stesso modo del form. Per consentire al modulo gestire gli eventi direttamente, è possibile utilizzare il multithreading. Per altre informazioni, vedere [Threading](../../programming-guide/concepts/threading/index.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)  
 [Istruzione AddHandler](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [Istruzione RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
