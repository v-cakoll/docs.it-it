---
title: 'Procedura dettagliata: modifica di un controllo composito con Visual C#'
ms.date: 03/30/2017
dev_langs:
- CSharp
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3ad9aad026a1a6a1266845736d7651db77fd5d5c
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546724"
---
# <a name="walkthrough-author-a-composite-control-with-c"></a>Procedura dettagliata: creazione di un controllo composito con CWalkthrough: Author a Composite Control with C\#

I controlli compositi consentono di creare e riutilizzare interfacce grafiche personalizzate. Un controllo composito è sostanzialmente un componente con rappresentazione visiva. Può essere composto da uno o più controlli per Windows Forms, componenti o blocchi di codice in grado di estenderne le funzionalità convalidando l'input dell'utente, modificando le proprietà della visualizzazione o effettuando altre attività richieste dall'autore. I controlli compositi possono essere inseriti in Windows Forms al pari degli altri controlli. Nella prima parte di questa procedura verrà creato un controllo composito semplice denominato `ctlClock`. Nella seconda parte, le funzionalità di `ctlClock` verranno estese mediante ereditarietà.

## <a name="create-the-project"></a>Creare il progetto

Quando si crea un nuovo progetto è necessario specificarne il nome per impostare lo spazio dei nomi radice, il nome dell'assembly e il nome del progetto e assicurarsi che il componente predefinito sia inserito nello spazio dei nomi corretto.

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a>Per creare la libreria di controlli ctlClockLib e il controllo ctlClock

1. In Visual Studio creare un nuovo progetto Libreria di controlli **Windows Form** e denominarlo **ctlClockLib**.

     Per impostazione predefinita il nome del progetto, `ctlClockLib`, verrà assegnato anche allo spazio dei nomi radice. Lo spazio dei nomi radice viene utilizzato per qualificare i nomi dei componenti dell'assembly. Se ad esempio due assembly forniscono componenti denominati `ctlClock`, sarà possibile specificare il componente `ctlClock` usando`ctlClockLib.ctlClock.`

2. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **UserControl1.cs**, quindi **scegliere Rinomina**. Modificare il nome file in `ctlClock.cs`. Fare clic sul pulsante **Sì** quando viene chiesto se si desidera rinominare tutti i riferimenti all'elemento di codice "UserControl1".

    > [!NOTE]
    > Per impostazione predefinita, un <xref:System.Windows.Forms.UserControl> controllo composito eredita dalla classe fornita dal sistema. La <xref:System.Windows.Forms.UserControl> classe fornisce le funzionalità richieste da tutti i controlli compositi e implementa metodi e proprietà standard.

3. Scegliere **Salva tutto** dal menu **File** per salvare il progetto.

## <a name="add-windows-controls-and-components-to-the-composite-control"></a>Aggiunta di controlli e componenti di Windows al controllo compositoAdd Windows Controls and Components to the Composite Control

L'interfaccia visiva è parte integrante del controllo composito e viene implementata mediante l'aggiunta di uno o più controlli Windows nell'area di progettazione. Nella procedura riportata di seguito i controlli Windows verranno incorporati nel controllo composito e verrà scritto il codice per l'implementazione delle funzionalità.

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a>Per aggiungere al controllo composito un oggetto Label e un oggetto Timer

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse **su ctlClock.cs**, quindi scegliere Visualizza finestra di **progettazione**.

2. Nella **Casella degli strumenti**espandere il nodo **Controlli comuni** , quindi fare doppio clic su **Etichetta**.

     Un <xref:System.Windows.Forms.Label> controllo `label1` denominato viene aggiunto al controllo nell'area di progettazione.

3. Nella finestra di progettazione fare clic su **label1**. Nella finestra Proprietà impostare le seguenti proprietà:

    |Proprietà|Modificare in|
    |--------------|---------------|
    |**Nome**|`lblDisplay`|
    |**Testo**|`(blank space)`|
    |**TextAlign**|`MiddleCenter`|
    |**Font.Size**|`14`|

4. Nella **Casella degli strumenti** espandere il nodo **Componenti**, quindi fare doppio clic su **Timer**.

     Poiché <xref:System.Windows.Forms.Timer> un oggetto è un componente, non dispone di alcuna rappresentazione visiva in fase di esecuzione. Pertanto, non viene visualizzato con i controlli nell'area di progettazione, ma piuttosto in **Progettazione componenti** (un vassoio nella parte inferiore dell'area di progettazione).

5. In **Progettazione componenti**fare clic su <xref:System.Windows.Forms.Timer.Interval%2A> **timer1**, quindi impostare la proprietà su `1000` e la <xref:System.Windows.Forms.Timer.Enabled%2A> proprietà su `true`.

     La <xref:System.Windows.Forms.Timer.Interval%2A> proprietà controlla la <xref:System.Windows.Forms.Timer> frequenza con cui il componente viene selezionato. Ogni volta che `timer1` scatta, viene eseguito il codice nell'evento `timer1_Tick`. L'intervallo rappresenta i millesimi di secondo che intercorrono tra uno scatto e l'altro.

6. In **Progettazione componenti**fare doppio clic su `timer1_Tick` **timer1** per passare all'evento per `ctlClock`.

7. Modificare il codice in modo che risulti simile al seguente. Assicurarsi di cambiare il modificatore di accesso da `private` a `protected`.

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     Questo codice determinerà la visualizzazione dell'ora corrente in `lblDisplay`. Poiché l'intervallo di `timer1` è stato impostato su `1000`, l'evento verrà generato ogni mille millesimi di secondo, aggiornando quindi l'ora corrente ogni secondo.

8. Modificare il metodo in modo che sia sottoponibile a override con la parola chiave `virtual`. Per ulteriori informazioni, vedere la sezione "Eredità da un controllo utente" riportata di seguito.

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. Scegliere **Salva tutto** dal menu **File** per salvare il progetto.

## <a name="add-properties-to-the-composite-control"></a>Aggiunta di proprietà al controllo compositoAdd Properties to the Composite Control

Il controllo orologio ora <xref:System.Windows.Forms.Label> incapsula <xref:System.Windows.Forms.Timer> un controllo e un componente, ognuno con il proprio set di proprietà intrinseche. Benché le singole proprietà di questi controlli non siano accessibili ai futuri utenti del controllo, è possibile creare ed esporre proprietà personalizzate scrivendo i blocchi di codice appropriati. Nella procedura riportata di seguito verrà illustrato come aggiungere al controllo proprietà che consentono all'utente di modificare il colore dello sfondo e del testo.

### <a name="to-add-a-property-to-your-composite-control"></a>Per aggiungere una proprietà al controllo composito

1. In **Esplora soluzioni**fare clic con il **pulsante**destro del mouse su ctlClock.cs , quindi **scegliere Visualizza codice**.

     Verrà aperto **l'editor** di codice per il controllo.

2. Individuare l'istruzione `public partial class ctlClock`. Sotto la parentesi graffa aperta (`{)`, digitare il codice seguente.

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     Queste istruzioni consentono di creare le variabili private da utilizzare per la memorizzazione dei valori delle proprietà che verranno create.

3. Immettere o incollare il codice seguente sotto le dichiarazioni di variabile del passaggio 2.

    ```csharp
    // Declares the name and type of the property.
    public Color ClockBackColor
    {
        // Retrieves the value of the private variable colBColor.
        get
        {
            return colBColor;
        }
        // Stores the selected value in the private variable colBColor, and
        // updates the background color of the label control lblDisplay.
        set
        {
            colBColor = value;
            lblDisplay.BackColor = colBColor;
        }
    }
    // Provides a similar set of instructions for the foreground color.
    public Color ClockForeColor
    {
        get
        {
            return colFColor;
        }
        set
        {
            colFColor = value;
            lblDisplay.ForeColor = colFColor;
        }
    }
    ```

     Nel codice riportato in precedenza vengono create due proprietà personalizzate, `ClockForeColor` e `ClockBackColor`, disponibili agli utenti successivi del controllo. Le istruzioni `get` e `set` consentono di archiviare e recuperare il valore della proprietà e di inserire il codice per implementare le funzionalità appropriate per la proprietà.

4. Scegliere **Salva tutto** dal menu **File** per salvare il progetto.

## <a name="test-the-control"></a>Testare il controllo

I controlli non sono applicazioni autonome e devono pertanto essere inseriti in un contenitore. Eseguire il test del comportamento del controllo in fase di esecuzione e sperimentare le proprietà con **UserControl Test Container**. Per altre informazioni, vedere [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).

### <a name="to-test-your-control"></a>Per eseguire il test del controllo

1. Premere **F5** per compilare il progetto ed eseguire il controllo in **UserControl Test Container**.

2. Nella griglia della proprietà di Test Container, selezionare la proprietà `ClockBackColor`, quindi fare clic sulla freccia a discesa per visualizzare la tavolozza dei colori.

3. Scegliere un colore facendovi clic sopra.

   Il colore di sfondo del controllo cambierà in base al colore selezionato.

4. Usare una sequenza di eventi simile per verificare il corretto funzionamento della proprietà `ClockForeColor`.

   In questa sezione e in quelle precedenti è stato illustrato come combinare componenti e controlli Windows con codici e package per aggiungere funzionalità personalizzate al modulo di un controllo composito. Si è inoltre appreso come esporre le proprietà del controllo composito e come eseguire il test del controllo dopo averlo completato. Nella sezione successiva verranno fornite informazioni sulla modalità di creazione di un controllo composito ereditato utilizzando `ctlClock` come base.

## <a name="inherit-from-a-composite-control"></a>Ereditare da un controllo compositoInherit from a Composite Control

Nelle sezioni precedenti si è appreso come combinare controlli, componenti e codice Windows in controlli compositi riutilizzabili. Il controllo composito può ora essere usato come base per la compilazione di altri controlli. Il processo di derivazione di una classe da una classe di base è detto *ereditarietà*. In questa sezione verrà creato un controllo composito denominato `ctlAlarmClock`. Il controllo verrà derivato dal relativo controllo padre, in questo caso `ctlClock`. Verrà spiegato come estendere le funzionalità di `ctlClock` mediante l'override dei metodi padre e l'aggiunta di nuovi metodi e proprietà.

Per creare un controllo ereditato, è innanzitutto necessario derivare il controllo dal relativo elemento padre. Questa operazione consente di creare un nuovo controllo, con le stesse proprietà, metodi e caratteristiche grafiche del controllo padre, che può essere anche utilizzato come base per l'aggiunta di una funzionalità nuova o modificata.

### <a name="to-create-the-inherited-control"></a>Per creare il controllo ereditato

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlClockLib**, **scegliere Aggiungi**, quindi Controllo **utente**.

     Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento** .

2. Selezionare il modello **Controllo utente ereditato**.

3. Nella casella **Nome** digitare `ctlAlarmClock.cs` e quindi fare clic su **Aggiungi**.

     Viene visualizzata la finestra di dialogo **Selezione ereditarietà**.

4. In **Nome componente** fare doppio clic su **ctlClock**.

5. In **Esplora soluzioni**scorrere i progetti correnti.

    > [!NOTE]
    > Nel progetto corrente è stato aggiunto il file denominato **ctlAlarmClock.cs**.

### <a name="add-the-alarm-properties"></a>Aggiungere le proprietà dell'allarme

Le modalità di aggiunta delle proprietà a un controllo ereditato sono analoghe a quelle utilizzate per i controlli compositi. Mediante la sintassi di dichiarazione delle proprietà si aggiungeranno ora al controllo due proprietà: `AlarmTime`, in cui viene memorizzato il valore della data e dell'ora in cui l'allarme deve essere disattivato, e `AlarmSet`, che indica se l'allarme è impostato o meno.

#### <a name="to-add-properties-to-your-composite-control"></a>Per aggiungere proprietà al controllo composito

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlAlarmClock**, quindi **scegliere Visualizza codice**.

2. Individuare l'istruzione `public class`. Si noti che il controllo eredita da `ctlClockLib.ctlClock`. Sotto la parentesi graffa aperta (`{)`, digitare il codice seguente.

    ```csharp
    private DateTime dteAlarmTime;
    private bool blnAlarmSet;
    // These properties will be declared as public to allow future
    // developers to access them.
    public DateTime AlarmTime
    {
        get
        {
            return dteAlarmTime;
        }
        set
        {
            dteAlarmTime = value;
        }
    }
    public bool AlarmSet
    {
        get
        {
            return blnAlarmSet;
        }
        set
        {
            blnAlarmSet = value;
        }
    }
    ```

### <a name="add-to-the-graphical-interface-of-the-control"></a>Aggiungi all'interfaccia grafica del controllo

Il controllo ereditato presenta un'interfaccia grafica identica a quella del controllo dal quale eredita e possiede gli stessi controlli costitutivi del controllo padre, ma le proprietà dei controlli costitutivi non sono disponibili, a meno che non siano state specificamente esposte. Analogamente a qualsiasi altro controllo composito, è possibile aggiungere elementi all'interfaccia grafica di un controllo composito ereditato, utilizzando la medesima procedura. In questo esempio verrà utilizzato un controllo label per aggiungere un effetto intermittente all'interfaccia grafica del controllo quando l'allarme suona.

#### <a name="to-add-the-label-control"></a>Per aggiungere il controllo label

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlAlarmClock**, quindi **scegliere Visualizza finestra di progettazione**.

     Nella finestra principale viene aperta la finestra di progettazione per `ctlAlarmClock`.

2. Fare clic sulla parte visualizzata del controllo e osservare la finestra Proprietà.

    > [!NOTE]
    > Tutte le proprietà sono presenti ma inattive, ossia visualizzate in grigio. Ciò indica che le proprietà sono native di `lblDisplay` e non è possibile accedervi né modificarle nella finestra Proprietà. Per impostazione predefinita i controlli contenuti in un controllo composito sono `private` e le relative proprietà non sono accessibili.

    > [!NOTE]
    > Se si desidera che gli utenti successivi del controllo composito abbiano accesso ai relativi controlli interni, dichiararli come `public` o `protected`. Sarà così possibile impostare e modificare le proprietà dei controlli contenuti nel controllo composito mediante il codice appropriato.

3. Aggiungere <xref:System.Windows.Forms.Label> un controllo al controllo composito.

4. Utilizzando il mouse, <xref:System.Windows.Forms.Label> trascinare il controllo immediatamente sotto la casella di visualizzazione. Nella finestra Proprietà impostare le seguenti proprietà:

    |Proprietà|Impostazione|
    |--------------|-------------|
    |**Nome**|`lblAlarm`|
    |**Testo**|**Allarme!**|
    |**TextAlign**|`MiddleCenter`|
    |**Visibile**|`false`|

### <a name="add-the-alarm-functionality"></a>Aggiungere la funzionalità di allarme

Nelle procedure precedenti sono state aggiunte proprietà e un controllo in grado di abilitare la funzionalità di allarme nel controllo composito. In questa procedura verrà aggiunto un codice che consente di confrontare l'ora corrente con l'ora dell'allarme e, se le ore risultano identiche, attivare un allarme lampeggiante. Eseguendo l'override del metodo `timer1_Tick` di `ctlClock` e aggiungendovi ulteriore codice sarà possibile estendere le capacità di `ctlAlarmClock` e conservare allo stesso le funzionalità intrinseche di `ctlClock`.

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a>Per eseguire l'override del metodo Timer1_Tick di ctlClock

1. Nell'**editor di codice ** individuare l'istruzione `private bool blnAlarmSet;` e aggiungere subito dopo la seguente istruzione.

    ```csharp
    private bool blnColorTicker;
    ```

2. Nell'**editor di codice** individuare la parentesi graffa di chiusura (`})`) alla fine della classe. Aggiungere il seguente codice prima della parentesi graffa.

    ```csharp
    protected override void timer1_Tick(object sender, System.EventArgs e)
    {
        // Calls the Timer1_Tick method of ctlClock.
        base.timer1_Tick(sender, e);
        // Checks to see if the alarm is set.
        if (AlarmSet == false)
            return;
        else
            // If the date, hour, and minute of the alarm time are the same as
            // the current time, flash an alarm.
        {
            if (AlarmTime.Date == DateTime.Now.Date && AlarmTime.Hour ==
                DateTime.Now.Hour && AlarmTime.Minute == DateTime.Now.Minute)
            {
                // Sets lblAlarmVisible to true, and changes the background color based on
                // the value of blnColorTicker. The background color of the label
                // will flash once per tick of the clock.
                lblAlarm.Visible = true;
                if (blnColorTicker == false)
                {
                    lblAlarm.BackColor = Color.Red;
                    blnColorTicker = true;
                }
                else
                {
                    lblAlarm.BackColor = Color.Blue;
                    blnColorTicker = false;
                }
            }
            else
            {
                // Once the alarm has sounded for a minute, the label is made
                // invisible again.
                lblAlarm.Visible = false;
            }
        }
    }
    ```

     Il codice appena aggiunto ha diverse funzioni. Se si utilizza l'istruzione `override`, il controllo utilizzerà questo metodo anziché il metodo ereditato dal controllo di base. Una volta chiamato, questo metodo chiamerà il metodo di cui esegue l'override utilizzando l'istruzione `base.timer1_Tick` e assicurando che tutte le funzionalità incorporate nel controllo originale vengano riprodotte in questo controllo. Verrà quindi eseguito il codice aggiuntivo per incorporare la funzionalità di allarme. Quando l'allarme viene attivato, verrà visualizzato un controllo label intermittente.

     Il controllo dell'allarme è quasi completo. L'unica operazione rimasta è l'implementazione di un sistema di disattivazione. A tal fine, è necessario aggiungere codice al metodo `lblAlarm_Click`.

#### <a name="to-implement-the-shutoff-method"></a>Per implementare il metodo di disattivazione

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse **su ctlAlarmClock.cs**, quindi scegliere Visualizza finestra di **progettazione**.

     Viene aperta la finestra di progettazione.

2. Aggiungere un pulsante al controllo. Impostare le proprietà del pulsante come illustrato di seguito.

    |Proprietà|valore|
    |--------------|-----------|
    |**Nome**|`btnAlarmOff`|
    |**Testo**|**Disabilita allarme**|

3. Nella finestra di progettazione fare doppio clic su **btnAlarmOff**.

     Nell'**editor di codice** verrà visualizzata la riga `private void btnAlarmOff_Click`.

4. Modificare il metodo in modo che risulti simile al seguente codice.

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. Scegliere **Salva tutto** dal menu **File** per salvare il progetto.

### <a name="use-the-inherited-control-on-a-form"></a>Utilizzare il controllo ereditato in un modulo

È possibile testare il controllo ereditato nello stesso `ctlClock`modo in cui è stato testato il controllo della classe base, : premere **F5** per compilare il progetto ed eseguire il controllo in **UserControl Test Container**. Per altre informazioni, vedere [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).

Per utilizzare il controllo è necessario inserirlo in un modulo. Come i controlli compositi standard, i controlli compositi ereditati non possono essere autonomi e devono essere inclusi in un modulo o in un altro contenitore. Poiché `ctlAlarmClock` include un maggior numero di funzionalità, per eseguire il test è necessario aggiungere del codice. In questa procedura verrà scritto un semplice programma per la verifica delle funzionalità di `ctlAlarmClock`. Verrà inoltre scritto il codice per impostare e visualizzare la proprietà `AlarmTime` di `ctlAlarmClock` e verrà eseguito il test delle funzionalità intrinseche del controllo.

#### <a name="to-build-and-add-your-control-to-a-test-form"></a>Per compilare e aggiungere il controllo a un modulo di test

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **ctlClockLib**, quindi **scegliere Compila**.

2. Aggiungere un nuovo progetto **applicazione Windows Form** alla soluzione e denominarlo **Test**.

3. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo **Riferimenti** per il progetto di test. Fare clic su **Aggiungi riferimento** per visualizzare la finestra di dialogo **Aggiungi riferimento**. Scegliere la scheda **Progetti**. Il progetto `ctlClockLib` verrà elencato in **Nome progetto**. Fare doppio clic sul progetto per cui si desidera aggiungere il riferimento al progetto di test.

4. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **Test**, quindi **scegliere Compila**.

5. Nella **Casella degli strumenti** espandere il nodo **Componenti ctlClockLib**.

6. Fare doppio clic su **ctlAlarmClock** per aggiungere una copia di `ctlAlarmClock` al modulo.

7. Nella **Casella degli strumenti**individuare e fare doppio <xref:System.Windows.Forms.DateTimePicker> clic su **DateTimePicker** per aggiungere un controllo al form, quindi aggiungere un <xref:System.Windows.Forms.Label> controllo facendo doppio clic su **Etichetta**.

8. Posizionare mediante il mouse i controlli in un punto del modulo di facile accesso.

9. Impostare le proprietà dei controlli come indicato di seguito.

    |Controllo|Proprietà|valore|
    |-------------|--------------|-----------|
    |`label1`|**Testo**|`(blank space)`|
    ||**Nome**|`lblTest`|
    |`dateTimePicker1`|**Nome**|`dtpTest`|
    ||**Format**|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. Nella finestra di progettazione fare doppio clic su **dtpTest**.

     Nell'**Editor di codice** viene visualizzato `private void dtpTest_ValueChanged`.

11. Modificare il codice in modo che risulti simile al seguente.

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **Test**, quindi scegliere Imposta come progetto **di avvio**.

13. Scegliere **Avvia** **debug**dal menu Debug .

     Verrà avviato il programma di test. Si noti che l'ora corrente viene aggiornata nel `ctlAlarmClock` <xref:System.Windows.Forms.DateTimePicker> controllo e che l'ora di inizio viene visualizzata nel controllo.

14. Fare <xref:System.Windows.Forms.DateTimePicker> clic sul punto in cui vengono visualizzati i minuti dell'ora.

15. Utilizzando la tastiera, impostare un valore per i minuti maggiore di un minuto rispetto all'ora corrente visualizzata da `ctlAlarmClock`.

     L'ora per l'impostazione dell'allarme è visualizzata in `lblTest`. Attendere che l'ora visualizzata raggiunga l'ora di impostazione dell'allarme. Quando l'ora visualizzata raggiunge l'ora su cui è impostato l'allarme `lblAlarm` lampeggerà.

16. Disattivare l'allarme facendo clic su `btnAlarmOff`. A questo punto è possibile reimpostare l'allarme.

In questo articolo sono stati trattati una serie di concetti chiave. Si è appreso come creare un controllo composito combinando controlli e componenti in un contenitore controllo composito e come aggiungere proprietà al controllo e scrivere il codice per l'implementazione di funzionalità personalizzate. Nell'ultima sezione sono state illustrate l'estensione delle funzionalità di uno specifico controllo composito mediante ereditarietà e la modifica delle funzionalità dei metodi host mediante override.

## <a name="see-also"></a>Vedere anche

- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
- [Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [Procedura dettagliata: eredità da un controllo di Windows Form con Visual C#](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
