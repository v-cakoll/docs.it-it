---
title: 'Procedura: Simulare eventi di mouse e tastiera nel codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
- mouse clicks [Windows Forms], simulating
- mouse [Windows Forms], event simulation
ms.assetid: 6abcb67e-3766-4af2-9590-bf5dabd17e41
ms.openlocfilehash: 52f89df8d7f28f0e00c3becd9005b46e52b5532c
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960207"
---
# <a name="how-to-simulate-mouse-and-keyboard-events-in-code"></a>Procedura: Simulare eventi di mouse e tastiera nel codice

Windows Form include diverse opzioni per simulare a livello di codice l'input del mouse e della tastiera. In questo argomento viene fornita una panoramica di queste opzioni.

## <a name="simulating-mouse-input"></a>Simulazione dell'input del mouse

Il modo migliore per simulare eventi del mouse consiste nel chiamare il metodo `On`*NomeEvento* che genera l'evento del mouse che si vuole simulare. Questa opzione è generalmente possibile solo all'interno di controlli e form personalizzati, perché i metodi che generano eventi sono protetti e non sono accessibili all'esterno del controllo o del form. Ad esempio, i passaggi seguenti illustrano come simulare il clic con il pulsante destro del mouse nel codice.

#### <a name="to-programmatically-click-the-right-mouse-button"></a>Per fare clic con il pulsante destro del mouse a livello di codice

1. Creare un oggetto <xref:System.Windows.Forms.MouseEventArgs> con la proprietà <xref:System.Windows.Forms.MouseEventArgs.Button%2A> impostata sul valore <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> .

2. Chiamare il metodo <xref:System.Windows.Forms.Control.OnMouseClick%2A> con <xref:System.Windows.Forms.MouseEventArgs> come argomento.

Per altre informazioni sui controlli personalizzati, vedere [Sviluppo di controlli Windows Form in fase di progettazione](./controls/developing-windows-forms-controls-at-design-time.md).

Esistono altri modi per simulare l'input del mouse. Ad esempio, è possibile impostare a livello di codice una proprietà di un controllo che rappresenta uno stato normalmente impostato tramite l'input del mouse (come la proprietà <xref:System.Windows.Forms.CheckBox.Checked%2A> del controllo <xref:System.Windows.Forms.CheckBox> ) oppure è possibile chiamare direttamente il delegato associato all'evento che si vuole simulare.

## <a name="simulating-keyboard-input"></a>Simulazione dell'input da tastiera

Anche se è possibile simulare l'input da tastiera usando le strategie descritte sopra per l'input del mouse, Windows Forms include anche la classe <xref:System.Windows.Forms.SendKeys> per inviare le pressioni di tasto all'applicazione attiva.

> [!CAUTION]
> Se l'applicazione verrà usata a livello internazionale con un'ampia gamma di tastiere, è opportuno evitare l'uso di <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> perché potrebbe generare risultati imprevedibili.

> [!NOTE]
> La classe <xref:System.Windows.Forms.SendKeys> è stata aggiornata per .NET Framework 3.0 per consentirne l'uso in applicazioni eseguite in Windows Vista. La sicurezza avanzata di Windows Vista (nota come Controllo dell'account utente) impedisce alla precedente implementazione di funzionare come previsto.
>
> La classe <xref:System.Windows.Forms.SendKeys> è soggetta a problemi di temporizzazione, che alcuni sviluppatori hanno dovuto risolvere. L'implementazione aggiornata è ancora soggetta a problemi di temporizzazione, ma è leggermente più veloce e può richiedere modifiche alle soluzioni alternative. La classe <xref:System.Windows.Forms.SendKeys> cerca di usare prima l'implementazione precedente e, se il tentativo non riesce, usa la nuova implementazione. Di conseguenza, il comportamento della classe <xref:System.Windows.Forms.SendKeys> potrebbe essere diverso a seconda del sistema operativo. Inoltre, quando la classe <xref:System.Windows.Forms.SendKeys> usa la nuova implementazione, il metodo <xref:System.Windows.Forms.SendKeys.SendWait%2A> non attenderà che i messaggi siano elaborati quando vengono inviati a un altro processo.
>
> Se l'applicazione si basa su un comportamento coerente indipendentemente dal sistema operativo, è possibile forzare la classe <xref:System.Windows.Forms.SendKeys> a usare la nuova implementazione aggiungendo la seguente impostazione applicazione al file app.config.
>
> ```xml
> <appSettings>
>  <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> Per forzare la classe <xref:System.Windows.Forms.SendKeys> a usare l'implementazione precedente, usare invece il valore `"JournalHook"` .

#### <a name="to-send-a-keystroke-to-the-same-application"></a>Per inviare una pressione di tasto alla stessa applicazione

1. Chiamare il metodo <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A> della classe <xref:System.Windows.Forms.SendKeys> . Le pressioni di tasti specificate verranno ricevute dal controllo attivo dell'applicazione. Il seguente esempio di codice usa <xref:System.Windows.Forms.SendKeys.Send%2A> per simulare la pressione del tasto INVIO quando l'utente fa doppio clic sulla superficie del form. Questo esempio presuppone un <xref:System.Windows.Forms.Form> con un solo controllo <xref:System.Windows.Forms.Button> con un indice di tabulazione 0.

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]

#### <a name="to-send-a-keystroke-to-a-different-application"></a>Per inviare una pressione di tasto a un'applicazione diversa

1. Attivare la finestra dell'applicazione che riceverà le pressioni di tasto e quindi chiamare il metodo <xref:System.Windows.Forms.SendKeys.Send%2A> o <xref:System.Windows.Forms.SendKeys.SendWait%2A> . Poiché non esiste alcun metodo gestito per attivare un'altra applicazione, è necessario usare i metodi Windows nativi per forzare lo stato attivo su altre applicazioni. Il seguente esempio di codice usa platform invoke per chiamare i metodi `FindWindow` e `SetForegroundWindow` per attivare la finestra dell'applicazione Calculator e quindi chiama <xref:System.Windows.Forms.SendKeys.SendWait%2A> per inviare una serie di calcoli all'applicazione Calculator.

    > [!NOTE]
    > I parametri corretti della chiamata a `FindWindow` che trova l'applicazione Calculator dipendono dalla versione di Windows.  Il codice seguente trova l'applicazione Calculator in Windows 7. In Windows Vista modificare il primo parametro in "SciCalc". È possibile usare lo strumento Spy++, incluso in Visual Studio, per determinare i parametri corretti.

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]

## <a name="example"></a>Esempio

L'esempio di codice seguente è l'applicazione completa degli esempi di codice precedenti.

[!code-cpp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.

## <a name="see-also"></a>Vedere anche

- [Input dell'utente in Windows Forms](user-input-in-windows-forms.md)
