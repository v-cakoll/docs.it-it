---
title: 'Procedura dettagliata: Creazione di un controllo composito con Visual Basic'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Visual Basic]
- user controls [Visual Basic]
- UserControl class [Windows Forms], walkthroughs
- user controls [Windows Forms], creating with Visual Basic
- controls [Windows Forms], composite controls
- composite controls [Windows Forms], creating
- custom controls [Windows Forms], creating
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
ms.openlocfilehash: 6404e5933f886578b4ad8afd0d3da324541fc3f9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299982"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a>Procedura dettagliata: Creazione di un controllo composito con Visual Basic
I controlli compositi consentono di creare e riutilizzare interfacce grafiche personalizzate. Un controllo composito è sostanzialmente un componente con rappresentazione visiva. Può essere composto da uno o più controlli per Windows Forms, componenti o blocchi di codice in grado di estenderne le funzionalità convalidando l'input dell'utente, modificando le proprietà della visualizzazione o effettuando altre attività richieste dall'autore. I controlli compositi possono essere inseriti in Windows Forms al pari degli altri controlli. Nella prima parte di questa procedura verrà creato un controllo composito semplice denominato `ctlClock`. Nella seconda parte, le funzionalità di `ctlClock` verranno estese mediante ereditarietà.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Quando si crea un nuovo progetto è necessario specificarne il nome per impostare lo spazio dei nomi radice, il nome dell'assembly e il nome del progetto e assicurarsi che il componente predefinito sia inserito nello spazio dei nomi corretto.  
  
#### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a>Per creare la libreria di controlli ctlClockLib e il controllo ctlClock  
  
1. Scegliere **Nuovo** dal menu **File**, quindi selezionare **Progetto** per aprire la finestra di dialogo **Nuovo progetto**.  
  
2. Nell'elenco dei progetti Visual Basic, selezionare la **libreria di controlli Windows** modello di progetto, digitare `ctlClockLib` nel **Name** casella e quindi fare clic su **OK**.  
  
     Per impostazione predefinita il nome del progetto, `ctlClockLib`, verrà assegnato anche allo spazio dei nomi radice. Lo spazio dei nomi radice viene utilizzato per qualificare i nomi dei componenti dell'assembly. Se, ad esempio, due assembly forniscono componenti denominati `ctlClock`, è possibile specificare il `ctlClock` componente usando `ctlClockLib.ctlClock.`  
  
3. In Esplora soluzioni fare clic con il pulsante destro del mouse su **UserControl1.vb**, quindi fare clic su **Rinomina**. Modificare il nome file in `ctlClock.vb`. Scegliere il pulsante **Sì** quando richiesto per rinominare tutti i riferimenti all'elemento di codice "UserControl1".  
  
    > [!NOTE]
    >  Per impostazione predefinita, un controllo composito eredita il <xref:System.Windows.Forms.UserControl> classe fornita dal sistema. Il <xref:System.Windows.Forms.UserControl> classe fornisce le funzionalità richieste da tutti i controlli compositi e implementa proprietà e metodi standard.  
  
4. Scegliere **Salva tutto** dal menu **File** per salvare il progetto.  
  
## <a name="adding-windows-controls-and-components-to-the-composite-control"></a>Aggiunta di componenti e controlli Windows al controllo composito  
 L'interfaccia visiva è parte integrante del controllo composito e viene implementata mediante l'aggiunta di uno o più controlli Windows nell'area di progettazione. Nella procedura riportata di seguito i controlli Windows verranno incorporati nel controllo composito e verrà scritto il codice per l'implementazione delle funzionalità.  
  
#### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a>Per aggiungere al controllo composito un oggetto Label e un oggetto Timer  
  
1. In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlClock.vb**, quindi scegliere **Progettazione viste**.  
  
2. Nella Casella degli strumenti espandere il nodo **Controlli comuni** e fare doppio clic su **Etichetta**.  
  
     Oggetto <xref:System.Windows.Forms.Label> controllo denominato `Label1` viene aggiunto al controllo nell'area di progettazione.  
  
3. Nella finestra di progettazione fare clic su **Label1**. Nella finestra Proprietà impostare le seguenti proprietà:  
  
    |Proprietà|Modificare in|  
    |--------------|---------------|  
    |**Nome**|`lblDisplay`|  
    |**Testo**|`(blank space)`|  
    |**TextAlign**|`MiddleCenter`|  
    |**Font.Size**|`14`|  
  
4. Nella **Casella degli strumenti** espandere il nodo **Componenti**, quindi fare doppio clic su **Timer**.  
  
     Poiché un <xref:System.Windows.Forms.Timer> è un componente, non dispone di alcuna rappresentazione visiva in fase di esecuzione. non verrà visualizzato insieme ai controlli nell'area di progettazione bensì in Progettazione componenti, una barra delle applicazioni disposta nella parte inferiore dell'area di progettazione.  
  
5. In Progettazione componenti fare clic su **Timer1**e quindi impostare il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà `1000` e il <xref:System.Windows.Forms.Timer.Enabled%2A> proprietà `True`.  
  
     Il <xref:System.Windows.Forms.Timer.Interval%2A> proprietà controlla la frequenza con cui scatta il componente timer. Ogni volta che `Timer1` scatta, viene eseguito il codice nell'evento `Timer1_Tick`. L'intervallo rappresenta i millesimi di secondo che intercorrono tra uno scatto e l'altro.  
  
6. In Progettazione componenti fare doppio clic su **Timer1** per passare all'evento `Timer1_Tick` di `ctlClock`.  
  
7. Modificare il codice in modo che risulti simile al seguente. Assicurarsi di cambiare il modificatore di accesso da `Private` a `Protected`.  
  
    ```vb  
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles Timer1.Tick  
        ' Causes the label to display the current time.    
        lblDisplay.Text = Format(Now, "hh:mm:ss")  
    End Sub  
    ```  
  
     Questo codice determinerà la visualizzazione dell'ora corrente in `lblDisplay`. Poiché l'intervallo di `Timer1` è stato impostato su `1000`, l'evento verrà generato ogni mille millesimi di secondo, aggiornando quindi l'ora corrente ogni secondo.  
  
8. Modificare il metodo in modo che sia sottoponibile a override. Per ulteriori informazioni, vedere la sezione "Eredità da un controllo utente" riportata di seguito.  
  
    ```vb  
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _  
        e As System.EventArgs) Handles Timer1.Tick  
    ```  
  
9. Scegliere **Salva tutto** dal menu **File** per salvare il progetto.  
  
## <a name="adding-properties-to-the-composite-control"></a>Aggiunta di proprietà al controllo composito  
 Il controllo orologio ora incapsula un' <xref:System.Windows.Forms.Label> controllo e un <xref:System.Windows.Forms.Timer> componente, ognuno con un proprio set di proprietà intrinseche. Benché le singole proprietà di questi controlli non siano accessibili ai futuri utenti del controllo, è possibile creare ed esporre proprietà personalizzate scrivendo i blocchi di codice appropriati. Nella procedura riportata di seguito verrà illustrato come aggiungere al controllo proprietà che consentono all'utente di modificare il colore dello sfondo e del testo.  
  
#### <a name="to-add-a-property-to-your-composite-control"></a>Per aggiungere una proprietà al controllo composito  
  
1. In Esplora soluzioni fare clic con il pulsante destro del mouse su c**tlClock.vb**, quindi scegliere **Visualizza codice**.  
  
     Verrà visualizzato l'editor del codice per il controllo.  
  
2. Individuare l'istruzione `Public Class ctlClock`. Sotto tale riga, aggiungere il seguente codice.  
  
    ```vb  
    Private colFColor as Color  
    Private colBColor as Color  
    ```  
  
     Queste istruzioni consentono di creare le variabili private da utilizzare per la memorizzazione dei valori delle proprietà che verranno create.  
  
3. Sotto le dichiarazioni delle variabili del passaggio 2 inserire il seguente codice.  
  
    ```vb  
    ' Declares the name and type of the property.  
    Property ClockBackColor() as Color  
        ' Retrieves the value of the private variable colBColor.  
        Get  
            Return colBColor  
        End Get  
        ' Stores the selected value in the private variable colBColor, and   
        ' updates the background color of the label control lblDisplay.  
        Set(ByVal value as Color)  
            colBColor = value  
            lblDisplay.BackColor = colBColor     
        End Set  
  
    End Property  
    ' Provides a similar set of instructions for the foreground color.  
    Property ClockForeColor() as Color  
        Get  
            Return colFColor  
        End Get  
        Set(ByVal value as Color)  
            colFColor = value  
            lblDisplay.ForeColor = colFColor  
        End Set  
    End Property  
    ```  
  
     Nel codice riportato in precedenza vengono create due proprietà personalizzate, `ClockForeColor` e `ClockBackColor`, disponibili agli utenti successivi del controllo mediante l'utilizzo dell'istruzione `Property`. Le istruzioni `Get` e `Set` consentono di archiviare e recuperare il valore della proprietà e di inserire il codice per implementare le funzionalità appropriate per la proprietà.  
  
4. Scegliere **Salva tutto** dal menu **File** per salvare il progetto.  
  
## <a name="testing-the-control"></a>Test del controllo  
 I controlli non sono progetti autonomi e devono pertanto essere inseriti in un contenitore. Eseguire il test del comportamento del controllo in fase di esecuzione e sperimentare le proprietà con **UserControl Test Container**. Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### <a name="to-test-your-control"></a>Per eseguire il test del controllo  
  
1. Per compilare il progetto ed eseguire il controllo in **UserControl Test Container**, premere F5.  
  
2. Nella griglia della proprietà di Test Container, selezionare la proprietà `ClockBackColor`, quindi fare clic sulla freccia a discesa per visualizzare la tavolozza dei colori.  
  
3. Scegliere un colore facendovi clic sopra.  
  
     Il colore di sfondo del controllo cambierà in base al colore selezionato.  
  
4. Usare una sequenza di eventi simile per verificare il corretto funzionamento della proprietà `ClockForeColor`.  
  
5. Per chiudere la finestra **UserControl Test Container**, scegliere **Chiudi**.  
  
     In questa sezione e in quelle precedenti è stato illustrato come combinare componenti e controlli Windows con codici e package per aggiungere funzionalità personalizzate al modulo di un controllo composito. Si è inoltre appreso come esporre le proprietà del controllo composito e come eseguire il test del controllo dopo averlo completato. Nella sezione successiva verranno fornite informazioni sulla modalità di creazione di un controllo composito ereditato utilizzando `ctlClock` come base.  
  
## <a name="inheriting-from-a-composite-control"></a>Eredità da un controllo composito  
 Nelle sezioni precedenti si è appreso come combinare controlli, componenti e codice Windows in controlli compositi riutilizzabili. Il controllo composito può ora essere usato come base per la compilazione di altri controlli. Il processo di derivazione di una classe da una classe di base è detto *ereditarietà*. In questa sezione verrà creato un controllo composito denominato `ctlAlarmClock`. Il controllo verrà derivato dal relativo controllo padre, in questo caso `ctlClock`. Verrà spiegato come estendere le funzionalità di `ctlClock` mediante l'override dei metodi padre e l'aggiunta di nuovi metodi e proprietà.  
  
 Per creare un controllo ereditato, è innanzitutto necessario derivare il controllo dal relativo elemento padre. Questa operazione consente di creare un nuovo controllo, con le stesse proprietà, metodi e caratteristiche grafiche del controllo padre, che può essere anche utilizzato come base per l'aggiunta di una funzionalità nuova o modificata.  
  
#### <a name="to-create-the-inherited-control"></a>Per creare il controllo ereditato  
  
1. In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlClockLib**, scegliere **Aggiungi**, quindi **Controllo utente**.  
  
     Viene aperta la finestra di dialogo **Aggiungi nuovo elemento**.  
  
2. Selezionare il modello **Controllo utente ereditato**.  
  
3. Nella casella **Nome** digitare `ctlAlarmClock.vb` e quindi fare clic su **Aggiungi**.  
  
     Viene visualizzata la finestra di dialogo **Selezione ereditarietà**.  
  
4. In **Nome componente** fare doppio clic su **ctlClock**.  
  
5. In Esplora soluzioni scorrere i progetti correnti.  
  
    > [!NOTE]
    >  Nel progetto corrente è stato aggiunto il file denominato **ctlAlarmClock.vb**.  
  
### <a name="adding-the-alarm-properties"></a>Aggiunta delle proprietà per l'allarme  
 Le modalità di aggiunta delle proprietà a un controllo ereditato sono analoghe a quelle utilizzate per i controlli compositi. Mediante la sintassi di dichiarazione delle proprietà si aggiungeranno ora al controllo due proprietà: `AlarmTime`, in cui viene memorizzato il valore della data e dell'ora in cui l'allarme deve essere disattivato, e `AlarmSet`, che indica se l'allarme è impostato o meno.  
  
##### <a name="to-add-properties-to-your-composite-control"></a>Per aggiungere proprietà al controllo composito  
  
1. In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock**, quindi scegliere **Visualizza codice**.  
  
2. Individuare la dichiarazione di classe per il controllo ctlAlarmClock, visualizzato come `Public Class ctlAlarmClock`.  Inserire il codice seguente nella dichiarazione di classe.  
  
    ```vb  
    Private dteAlarmTime As Date  
    Private blnAlarmSet As Boolean  
    ' These properties will be declared as Public to allow future   
    ' developers to access them.  
    Public Property AlarmTime() As Date  
        Get  
            Return dteAlarmTime  
        End Get  
        Set(ByVal value as Date)  
            dteAlarmTime = value  
        End Set  
    End Property  
    Public Property AlarmSet() As Boolean  
        Get  
            Return blnAlarmSet  
        End Get  
        Set(ByVal value as Boolean)  
            blnAlarmSet = value  
        End Set  
    End Property  
    ```  
  
### <a name="adding-to-the-graphical-interface-of-the-control"></a>Aggiunta del controllo all'interfaccia grafica  
 Il controllo ereditato presenta un'interfaccia grafica identica a quella del controllo dal quale eredita e possiede gli stessi controlli costitutivi del controllo padre, ma le proprietà dei controlli costitutivi non sono disponibili, a meno che non siano state specificamente esposte. Analogamente a qualsiasi altro controllo composito, è possibile aggiungere elementi all'interfaccia grafica di un controllo composito ereditato, utilizzando la medesima procedura. In questo esempio verrà utilizzato un controllo label per aggiungere un effetto intermittente all'interfaccia grafica del controllo quando l'allarme suona.  
  
##### <a name="to-add-the-label-control"></a>Per aggiungere il controllo label  
  
1. In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock** e scegliere **Visualizza finestra di progettazione**.  
  
     Nella finestra principale viene aperta la finestra di progettazione per `ctlAlarmClock`.  
  
2. Fare clic su `lblDisplay` (parte visualizzata del controllo) e osservare la finestra Proprietà.  
  
    > [!NOTE]
    >  Tutte le proprietà sono presenti ma inattive, ossia visualizzate in grigio. Ciò indica che le proprietà sono native di `lblDisplay` e non è possibile accedervi né modificarle nella finestra Proprietà. Per impostazione predefinita i controlli contenuti in un controllo composito sono `Private` e le relative proprietà non sono accessibili.  
  
    > [!NOTE]
    >  Se si desidera che gli utenti successivi del controllo composito abbiano accesso ai relativi controlli interni, dichiararli come `Public` o `Protected`. Sarà così possibile impostare e modificare le proprietà dei controlli contenuti nel controllo composito mediante il codice appropriato.  
  
3. Aggiungere un <xref:System.Windows.Forms.Label> controllo al controllo composito.  
  
4. Usando il mouse, trascinare il <xref:System.Windows.Forms.Label> controllo immediatamente di sotto della visualizzazione. Nella finestra Proprietà impostare le seguenti proprietà:  
  
    |Proprietà|Impostazione|  
    |--------------|-------------|  
    |**Nome**|`lblAlarm`|  
    |**Testo**|**Allarme!**|  
    |**TextAlign**|`MiddleCenter`|  
    |**Visibile**|`False`|  
  
### <a name="adding-the-alarm-functionality"></a>Aggiunta della funzionalità di allarme  
 Nelle procedure precedenti sono state aggiunte proprietà e un controllo in grado di abilitare la funzionalità di allarme nel controllo composito. In questa procedura verrà aggiunto un codice che consente di confrontare l'ora corrente con l'ora dell'allarme e, se le ore risultano identiche, attivare un allarme sonoro e lampeggiante. Eseguendo l'override del metodo `Timer1_Tick` di `ctlClock` e aggiungendovi ulteriore codice sarà possibile estendere le capacità di `ctlAlarmClock` e conservare allo stesso le funzionalità intrinseche di `ctlClock`.  
  
##### <a name="to-override-the-timer1tick-method-of-ctlclock"></a>Per eseguire l'override del metodo Timer1_Tick di ctlClock  
  
1. In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock.vb**, quindi scegliere **Visualizza codice**.  
  
2. Individuare l'istruzione `Private blnAlarmSet As Boolean`. e aggiungere subito dopo la seguente istruzione.  
  
    ```vb  
    Dim blnColorTicker as Boolean  
    ```  
  
3. Individuare l'istruzione `End Class` nella parte inferiore della pagina. Prima dell'istruzione `End Class` aggiungere il seguente codice.  
  
    ```vb  
    Protected Overrides Sub Timer1_Tick(ByVal sender As Object, ByVal e _  
        As System.EventArgs)  
        ' Calls the Timer1_Tick method of ctlClock.  
        MyBase.Timer1_Tick(sender, e)  
        ' Checks to see if the Alarm is set.  
        If AlarmSet = False Then  
            Exit Sub  
        End If  
        ' If the date, hour, and minute of the alarm time are the same as  
        ' now, flash and beep an alarm.   
        If AlarmTime.Date = Now.Date And AlarmTime.Hour = Now.Hour And _  
            AlarmTime.Minute = Now.Minute Then  
            ' Sounds an audible beep.  
            Beep()  
            ' Sets lblAlarmVisible to True, and changes the background color based on the   
            ' value of blnColorTicker. The background color of the label will   
            ' flash once per tick of the clock.  
            lblAlarm.Visible = True  
            If blnColorTicker = False Then  
                lblAlarm.BackColor = Color.PeachPuff  
                blnColorTicker = True  
            Else  
                lblAlarm.BackColor = Color.Plum  
                blnColorTicker = False  
            End If  
        Else  
            ' Once the alarm has sounded for a minute, the label is made   
            ' invisible again.  
            lblAlarm.Visible = False  
        End If  
    End Sub  
    ```  
  
     Il codice appena aggiunto ha diverse funzioni. Se si utilizza l'istruzione `Overrides`, il controllo utilizzerà questo metodo anziché il metodo ereditato dal controllo di base. Una volta chiamato, questo metodo chiamerà il metodo di cui esegue l'override utilizzando l'istruzione `MyBase.Timer1_Tick` e assicurando che tutte le funzionalità incorporate nel controllo originale vengano riprodotte in questo controllo. Verrà quindi eseguito il codice aggiuntivo per incorporare la funzionalità di allarme. Quando l'allarme viene attivato, viene visualizzato un controllo etichetta lampeggiante e viene emesso un segnale acustico.  
  
    > [!NOTE]
    >  Poiché si esegue l'override di un gestore eventi ereditato, non è necessario specificare l'evento tramite la parola chiave `Handles`. L'evento risulta già associato. L'override riguarda l'implementazione del gestore.  
  
     Il controllo dell'allarme è quasi completo. L'unica operazione rimasta è l'implementazione di un sistema di disattivazione. A tal fine, è necessario aggiungere codice al metodo `lblAlarm_Click`.  
  
##### <a name="to-implement-the-shutoff-method"></a>Per implementare il metodo di disattivazione  
  
1. In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlAlarmClock.vb**, quindi scegliere **Visualizza finestra di progettazione**.  
  
2. Nella finestra di progettazione fare doppio clic sul controllo **lblAlarm**. Nell'**editor di codice** verrà visualizzata la riga `Private Sub lblAlarm_Click`.  
  
3. Modificare il metodo in modo che risulti simile al seguente codice.  
  
    ```vb  
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _  
     System.EventArgs) Handles lblAlarm.Click  
        ' Turns off the alarm.  
        AlarmSet = False  
        ' Hides the flashing label.  
        lblAlarm.Visible = False  
    End Sub  
    ```  
  
4. Scegliere **Salva tutto** dal menu **File** per salvare il progetto.  
  
### <a name="using-the-inherited-control-on-a-form"></a>Utilizzo del controllo ereditato in un modulo  
 È possibile testare il controllo ereditato esattamente come si esegue il controllo di classe di base, `ctlClock`: Per compilare il progetto ed eseguire il controllo in **UserControl Test Container**, premere F5. Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
 Per utilizzare il controllo è necessario inserirlo in un modulo. Come i controlli compositi standard, i controlli compositi ereditati non possono essere autonomi e devono essere inclusi in un modulo o in un altro contenitore. Poiché `ctlAlarmClock` include un maggior numero di funzionalità, per eseguire il test è necessario aggiungere del codice. In questa procedura verrà scritto un semplice programma per la verifica delle funzionalità di `ctlAlarmClock`. Verrà inoltre scritto il codice per impostare e visualizzare la proprietà `AlarmTime` di `ctlAlarmClock` e verrà eseguito il test delle funzionalità intrinseche del controllo.  
  
##### <a name="to-build-and-add-your-control-to-a-test-form"></a>Per compilare e aggiungere il controllo a un modulo di test  
  
1. In Esplora soluzioni fare clic con il pulsante destro del mouse su **ctlClockLib**, quindi scegliere **Compila**.  
  
2. Scegliere **Aggiungi** dal menu **File**e quindi fare clic su **Nuovo progetto**.  
  
3. Aggiungere un nuovo progetto **Applicazione Windows** alla soluzione e denominarlo `Test`.  
  
     Il progetto **Test** verrà aggiunto a Esplora soluzioni.  
  
4. In Esplora soluzioni fare clic con il pulsante destro del mouse sul nodo di progetto `Test`, quindi scegliere **Aggiungi riferimento** per visualizzare la finestra di dialogo **Aggiungi riferimento**.  
  
5. Scegliere la scheda **Progetti**. Il progetto **ctlClockLib** verrà elencato in **Nome progetto**. Fare doppio clic su **ctlClockLib** per aggiungere il riferimento al progetto di test.  
  
6. In Esplora soluzioni fare clic con il pulsante destro del mouse su **Test**, quindi scegliere **Compila**.  
  
7. Nella **Casella degli strumenti** espandere il nodo **Componenti ctlClockLib**.  
  
8. Fare doppio clic su **ctlAlarmClock** per aggiungere un'istanza di `ctlAlarmClock` al modulo.  
  
9. Nel **casella degli strumenti**individuare e fare doppio clic su **DateTimePicker** per aggiungere un <xref:System.Windows.Forms.DateTimePicker> controllo al form e quindi aggiungere un <xref:System.Windows.Forms.Label> facendo doppio clic sui **etichetta**.  
  
10. Posizionare mediante il mouse i controlli in un punto del modulo di facile accesso.  
  
11. Impostare le proprietà dei controlli come indicato di seguito.  
  
    |Control|Proprietà|Value|  
    |-------------|--------------|-----------|  
    |`label1`|**Testo**|`(blank space)`|  
    ||**Nome**|`lblTest`|  
    |`dateTimePicker1`|**Nome**|`dtpTest`|  
    ||**Formato**|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|  
  
12. Nella finestra di progettazione fare doppio clic su **dtpTest**.  
  
     Nell'**Editor di codice** viene visualizzato `Private Sub dtpTest_ValueChanged`.  
  
13. Modificare il codice in modo che risulti simile al seguente.  
  
    ```vb  
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles dtpTest.ValueChanged  
        ctlAlarmClock1.AlarmTime = dtpTest.Value  
        ctlAlarmClock1.AlarmSet = True  
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _  
            "hh:mm")  
    End Sub  
    ```  
  
14. In Esplora soluzioni fare clic con il pulsante destro del mouse su **Test** e scegliere **Imposta come progetto di avvio**.  
  
15. Scegliere **Avvia debug** dal menu **Debug**.  
  
     Verrà avviato il programma di test. Si noti che l'ora corrente viene aggiornata nel `ctlAlarmClock` controllo e l'ora di inizio viene visualizzato nei <xref:System.Windows.Forms.DateTimePicker> controllo.  
  
16. Fare clic su di <xref:System.Windows.Forms.DateTimePicker> vengono visualizzati i minuti dell'ora.  
  
17. Utilizzando la tastiera, impostare un valore per i minuti maggiore di un minuto rispetto all'ora corrente visualizzata da `ctlAlarmClock`.  
  
     L'ora per l'impostazione dell'allarme è visualizzata in `lblTest`. Attendere che l'ora visualizzata raggiunga l'ora di impostazione dell'allarme. Quando l'ora visualizzata raggiunge l'ora su cui è impostato l'allarme, verrà emesso un segnale acustico e `lblAlarm` lampeggerà.  
  
18. Disattivare l'allarme facendo clic su `lblAlarm`. A questo punto è possibile reimpostare l'allarme.  
  
     In questa procedura dettagliata sono stati trattati diversi concetti chiave. Si è appreso come creare un controllo composito combinando controlli e componenti in un contenitore controllo composito e come aggiungere proprietà al controllo e scrivere il codice per l'implementazione di funzionalità personalizzate. Nell'ultima sezione sono state illustrate l'estensione delle funzionalità di uno specifico controllo composito mediante ereditarietà e la modifica delle funzionalità dei metodi host mediante override.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
- [Procedura: Creare controlli compositi](how-to-author-composite-controls.md)
- [Procedura: Visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
