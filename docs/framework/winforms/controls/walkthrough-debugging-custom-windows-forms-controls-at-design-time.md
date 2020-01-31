---
title: Debug di controlli personalizzati in fase di progettazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9e292a1219c24571bcb35db2fe357b0197c8812
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740192"
---
# <a name="walkthrough-debug-custom-windows-forms-controls-at-design-time"></a>Procedura dettagliata: debug di controlli di Windows Forms personalizzati in fase di progettazione

Quando si crea un controllo personalizzato, sarà spesso necessario eseguire il debug del comportamento in fase di progettazione. Questo vale soprattutto se si crea una finestra di progettazione personalizzata per il controllo personalizzato. Per informazioni dettagliate, vedere [procedura dettagliata: creazione di un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione di Visual Studio](creating-a-wf-control-design-time-features.md).

È possibile eseguire il debug dei controlli personalizzati con Visual Studio, proprio come per qualsiasi altra classe .NET Framework. La differenza è che si eseguirà il debug di un'istanza separata di Visual Studio che esegue il codice del controllo personalizzato.

## <a name="create-the-project"></a>Creare il progetto

Il primo passaggio consiste nel creare il progetto dell'applicazione. Questo progetto verrà usato per compilare l'applicazione che ospita il controllo personalizzato.

In Visual Studio creare un progetto di applicazione Windows e denominarlo **DebuggingExample**.

## <a name="create-the-control-library-project"></a>Creare il progetto di libreria di controlli

1. Aggiungere un progetto **libreria di controlli Windows** alla soluzione.

2. Aggiungere un nuovo elemento **UserControl** al progetto DebugControlLibrary. Denominarlo **DebugControl**.

3. In **Esplora soluzioni**eliminare il controllo predefinito del progetto eliminando il file di codice con un nome di base di UserControl1.

4. Compila la soluzione.

## <a name="checkpoint"></a>Punto di controllo

A questo punto, sarà possibile visualizzare il controllo personalizzato nella **casella degli strumenti**.

Per controllare lo stato di avanzamento, trovare la nuova scheda denominata **DebugControlLibrary Components** e fare clic per selezionarla. Quando si apre, il controllo verrà visualizzato come **DebugControl** con l'icona predefinita accanto.

## <a name="add-a-property-to-your-custom-control"></a>Aggiungere una proprietà al controllo personalizzato

Per dimostrare che il codice del controllo personalizzato viene eseguito in fase di progettazione, si aggiungerà una proprietà e si imposterà un punto di interruzione nel codice che implementa la proprietà.

1. Aprire **DebugControl** nell' **editor di codice**. Aggiungere il codice seguente alla definizione della classe:

    ```vb
    Private demoStringValue As String = Nothing
    <BrowsableAttribute(true)>
    Public Property DemoString() As String

        Get
            Return Me.demoStringValue
        End Get

        Set(ByVal value As String)
            Me.demoStringValue = value
        End Set

    End Property
    ```

    ```csharp
    private string demoStringValue = null;
    [Browsable(true)]
    public string DemoString
    {
        get
        {
            return this.demoStringValue;
        }
        set
        {
            demoStringValue = value;
        }
    }
    ```

2. Compila la soluzione.

## <a name="add-your-custom-control-to-the-host-form"></a>Aggiungere il controllo personalizzato al modulo host

Per eseguire il debug del comportamento in fase di progettazione del controllo personalizzato, è necessario inserire un'istanza della classe del controllo personalizzato in un form host.

1. Nel progetto "DebuggingExample" aprire Form1 nel **Progettazione Windows Form**.

2. Nella **casella degli strumenti**aprire la scheda **componenti di DebugControlLibrary** e trascinare un'istanza di **DebugControl** nel form.

3. Trovare la proprietà personalizzata `DemoString` nella finestra **Proprietà** . Si noti che è possibile modificare il valore come qualsiasi altra proprietà. Si noti inoltre che quando si seleziona la proprietà `DemoString`, la stringa di descrizione della proprietà viene visualizzata nella parte inferiore della finestra **Proprietà** .

## <a name="set-up-the-project-for-design-time-debugging"></a>Configurare il progetto per il debug in fase di progettazione

Per eseguire il debug del comportamento in fase di progettazione del controllo personalizzato, si eseguirà il debug di un'istanza separata di Visual Studio che esegue il codice del controllo personalizzato.

1. Fare clic con il pulsante destro del mouse sul progetto **DebugControlLibrary** nel **Esplora soluzioni** e scegliere **proprietà**.

2. Nella finestra delle proprietà di **DebugControlLibrary** selezionare la scheda **debug** .

     Nella sezione **azione di avvio** selezionare **Avvia programma esterno**. Si eseguirà il debug di un'istanza separata di Visual Studio, quindi fare clic sui puntini di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante Finestra Proprietà di Visual Studio](./media/visual-studio-ellipsis-button.png)) per cercare l'IDE di Visual Studio. Il nome del file eseguibile è **devenv. exe**e, se è stato installato nel percorso predefinito, il percorso è *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<Edition > \Common7\IDE*.

3. Fare clic su **OK** per chiudere la finestra di dialogo.

4. Fare clic con il pulsante destro del mouse sul progetto **DebugControlLibrary** e selezionare **Imposta come progetto di avvio** per abilitare questa configurazione di debug.

## <a name="debug-your-custom-control-at-design-time"></a>Eseguire il debug del controllo personalizzato in fase di progettazione

A questo punto si è pronti per eseguire il debug del controllo personalizzato durante l'esecuzione in modalità progettazione. Quando si avvia la sessione di debug, viene creata una nuova istanza di Visual Studio che verrà utilizzata per caricare la soluzione "DebuggingExample". Quando si apre Form1 in **progettazione form**, verrà creata un'istanza del controllo personalizzato che inizierà a essere in esecuzione.

1. Aprire il file di origine **DebugControl** nell' **editor di codice** e inserire un punto di interruzione nella funzione di accesso `Set` della proprietà `DemoString`.

2. Premere **F5** per avviare la sessione di debug. Viene creata una nuova istanza di Visual Studio. È possibile distinguere tra le istanze in due modi:

    - Nell'istanza di debug è presente la parola in **esecuzione** nella relativa barra del titolo.

    - L'istanza di debug dispone del pulsante **Avvia** sulla barra degli strumenti di **debug** disabilitata

   Il punto di interruzione viene impostato nell'istanza di debug.

3. Nella nuova istanza di Visual Studio aprire la soluzione "DebuggingExample". È possibile trovare facilmente la soluzione selezionando **progetti recenti** dal menu **file** . Il file di soluzione "DebuggingExample. sln" verrà elencato come file usato più di recente.

4. Aprire Form1 in **progettazione form** e selezionare il controllo **DebugControl** .

5. Modificare il valore della proprietà `DemoString` . Quando si esegue il commit della modifica, l'istanza di debug di Visual Studio acquisisce lo stato attivo e l'esecuzione si arresta in corrispondenza del punto di interruzione. È possibile eseguire la funzione di accesso alla proprietà solo come qualsiasi altro codice.

6. Per arrestare il debug, chiudere l'istanza ospitata di Visual Studio oppure selezionare il pulsante **Interrompi debug** nell'istanza di debug.

## <a name="next-steps"></a>Passaggi successivi

Ora che è possibile eseguire il debug dei controlli personalizzati in fase di progettazione, esistono molte possibilità per espandere l'interazione del controllo con l'IDE di Visual Studio.

- È possibile utilizzare la proprietà <xref:System.ComponentModel.Component.DesignMode%2A> della classe <xref:System.ComponentModel.Component> per scrivere codice che verrà eseguito solo in fase di progettazione. Per informazioni dettagliate, vedere <xref:System.ComponentModel.Component.DesignMode%2A>.

- Sono disponibili diversi attributi che è possibile applicare alle proprietà del controllo per modificare l'interazione del controllo personalizzato con la finestra di progettazione. È possibile trovare questi attributi nello spazio dei nomi <xref:System.ComponentModel?displayProperty=nameWithType>.

- È possibile scrivere una finestra di progettazione personalizzata per il controllo personalizzato. Questo consente di controllare completamente l'esperienza di progettazione usando l'infrastruttura di progettazione estendibile esposta da Visual Studio. Per informazioni dettagliate, vedere [procedura dettagliata: creazione di un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione di Visual Studio](creating-a-wf-control-design-time-features.md).

## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Creazione di un controllo Windows Form che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione](creating-a-wf-control-design-time-features.md)
