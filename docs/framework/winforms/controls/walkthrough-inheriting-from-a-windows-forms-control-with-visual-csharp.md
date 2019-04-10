---
title: 'Procedura dettagliata: Eredità da un controllo di Windows Form con Visual C#'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
ms.openlocfilehash: cafd8685f34537f8efb372967dc45682afbe8fa0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306378"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-c"></a>Procedura dettagliata: Eredità da un controllo di Windows Forms con Visual C\#
[!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)] consente di creare controlli personalizzati avanzati sfruttando *l'ereditarietà*. L'ereditarietà consente di creare nuovi controlli che non solo conservano tutte le funzionalità proprie dei controlli Windows Forms standard, ma includono anche funzionalità personalizzate. In questa procedura verrà creato un controllo ereditato semplice denominato `ValueButton`. Questo pulsante eredita la funzionalità di standard di Windows Form <xref:System.Windows.Forms.Button> controllare ed espone una proprietà personalizzata denominata `ButtonValue`.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Quando si crea un nuovo progetto è necessario specificarne il nome per impostare lo spazio dei nomi radice, il nome dell'assembly e il nome del progetto e assicurarsi che il componente predefinito sia inserito nello spazio dei nomi corretto.  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a>Per creare la libreria di controlli ValueButtonLib e il controllo ValueButton  
  
1. Scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**. Verrà visualizzata la finestra di dialogo **Nuovo progetto**.  
  
2. Selezionare il **libreria di controlli Windows Form** modello di progetto dall'elenco dei progetti Visual c# e digitare `ValueButtonLib` nel **nome** casella.  
  
     Per impostazione predefinita il nome del progetto, `ValueButtonLib`, verrà assegnato anche allo spazio dei nomi radice. Lo spazio dei nomi radice viene utilizzato per qualificare i nomi dei componenti dell'assembly. Se ad esempio due assembly forniscono componenti denominati `ValueButton`, sarà possibile specificare il componente `ValueButton` utilizzando `ValueButtonLib.ValueButton`. Per altre informazioni, vedere [Spazi dei nomi](../../../csharp/programming-guide/namespaces/index.md).  
  
3. In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **UserControl1.cs** e scegliere **Rinomina** dal menu di scelta rapida. Modificare il nome file in `ValueButton.cs`. Scegliere il pulsante **Sì** quando richiesto per rinominare tutti i riferimenti all'elemento di codice '`UserControl1`'.  
  
4. In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **ValueButton.cs** e scegliere **Visualizza codice**.  
  
5. Individuare il `class` linea, informativa `public partial class ValueButton`e modificare il tipo dal quale il controllo eredita da <xref:System.Windows.Forms.UserControl> a <xref:System.Windows.Forms.Button>. In questo modo il controllo ereditato potrà ereditare tutte le funzionalità del <xref:System.Windows.Forms.Button> controllo.  
  
6. In **Esplora soluzioni** aprire il nodo **ValueButton.cs** per visualizzare il file del codice generato nella finestra di progettazione **ValueButton.Designer.cs**. Aprire il file nell'**editor di codice**.  
  
7. Individuare il `InitializeComponent` metodo e rimuovere la riga che assegna il <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> proprietà. Questa proprietà non esiste nel <xref:System.Windows.Forms.Button> controllo.  
  
8. Per salvare il progetto, scegliere **Salva tutto** dal menu **File**.  
  
    > [!NOTE]
    >  Non è più disponibile alcuna finestra di progettazione. Poiché il <xref:System.Windows.Forms.Button> controllo gestisce la propria visualizzazione, non è possibile modificarne l'aspetto nella finestra di progettazione. La rappresentazione visiva sarà esattamente uguale a quello della classe eredita da (vale a dire <xref:System.Windows.Forms.Button>) a meno che non modificata nel codice. È comunque possibile aggiungere nell'area di progettazione i componenti che non dispongono di elementi dell'interfaccia utente.  
  
## <a name="adding-a-property-to-your-inherited-control"></a>Aggiunta di una proprietà al controllo ereditato  
 Un possibile utilizzo dei controlli Windows Forms ereditati è la creazione di controlli aventi aspetto e funzionalità identici ai controlli standard Windows Forms, ma che espongono proprietà personalizzate. In questa sezione verrà illustrata la modalità di aggiunta della proprietà `ButtonValue` al controllo.  
  
#### <a name="to-add-the-value-property"></a>Per aggiungere la proprietà Value  
  
1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **ValueButton.cs**, quindi scegliere **Visualizza codice** dal menu di scelta rapida.  
  
2. Individuare l'istruzione `class`. Sotto `{` digitare il seguente codice:  
  
    ```csharp  
    // Creates the private variable that will store the value of your   
    // property.  
    private int varValue;  
    // Declares the property.  
    public int ButtonValue  
    {  
       // Sets the method for retrieving the value of your property.  
       get  
       {  
          return varValue;  
       }  
       // Sets the method for setting the value of your property.  
       set  
       {  
          varValue = value;  
       }  
    }  
    ```  
  
     Questo codice consente di impostare i metodi per la memorizzazione e il recupero della proprietà `ButtonValue`. L'istruzione `get` consente di impostare il valore restituito sul valore memorizzato nella variabile privata `varValue`, mentre l'istruzione `set` consente di impostare il valore della variabile privata mediante la parola chiave `value`.  
  
3. Per salvare il progetto, scegliere **Salva tutto** dal menu **File**.  
  
## <a name="testing-your-control"></a>Test del controllo  
 I controlli non sono progetti autonomi e devono pertanto essere inseriti in un contenitore. Per testare il controllo, è necessario creare un progetto di test in cui eseguirlo. È inoltre necessario rendere il controllo accessibile al progetto di test compilandolo. In questa sezione verrà illustrato come compilare un controllo ed eseguirne il test in un Windows Form.  
  
#### <a name="to-build-your-control"></a>Per compilare il controllo  
  
1. Scegliere **Compila soluzione** dal menu **Compila**.  
  
     La compilazione dovrebbe essere completata senza errori del compilatore o avvisi.  
  
#### <a name="to-create-a-test-project"></a>Per creare un progetto di test  
  
1. Scegliere **Aggiungi** dal menu **File**, quindi fare clic su **Nuovo progetto**. Verrà visualizzata la finestra di dialogo **Aggiungi nuovo progetto**.  
  
2. Selezionare il nodo **Windows** sotto il nodo **Visual C#** e fare clic su **Windows Forms Application**.  
  
3. Nella casella **Nome** digitare `Test`.  
  
4. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Riferimenti** del progetto di test, quindi scegliere **Aggiungi riferimento** dal menu di scelta rapida per visualizzare la finestra di dialogo **Aggiungi riferimento**.  
  
5. Scegliere la scheda **Progetti**. Il progetto `ValueButtonLib` verrà elencato in **Nome progetto**. Fare doppio clic sul progetto per cui si desidera aggiungere il riferimento al progetto di test.  
  
6. In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Test** e scegliere **Compila**.  
  
#### <a name="to-add-your-control-to-the-form"></a>Per aggiungere il controllo al modulo  
  
1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Form1.cs**, quindi scegliere **Visualizza finestra di progettazione** dal menu di scelta rapida.  
  
2. Nella **Casella degli strumenti** fare clic su **Componenti ValueButtonLib**. Fare doppio clic su **ValueButton**.  
  
     Nel modulo verrà visualizzato un controllo **ValueButton**.  
  
3. Fare clic con il pulsante destro del mouse su **ValueButton**, quindi scegliere **Proprietà** dal menu di scelta rapida.  
  
4. Nella finestra **Proprietà** esaminare le proprietà del controllo. Tali proprietà sono identiche a quelle esposte da un pulsante standard, con la differenza che è disponibile anche la proprietà `ButtonValue`.  
  
5. Impostare la proprietà `ButtonValue` su `5`.  
  
6. Nel **tutti i Windows Form** scheda della finestra di **della casella degli strumenti**, fare doppio clic su **etichetta** per aggiungere un <xref:System.Windows.Forms.Label> controllo al form.  
  
7. Posizionare l'etichetta al centro del modulo.  
  
8. Doppio clic su `valueButton1`.  
  
     Nell'**editor di codice** verrà visualizzato l'evento `valueButton1_Click`.  
  
9. Inserire la seguente riga di codice.  
  
    ```csharp  
    label1.Text = valueButton1.ButtonValue.ToString();  
    ```  
  
10. In **Esplora soluzioni** fare clic con il pulsante destro del mouse su **Test** quindi scegliere **Imposta** come progetto di avvio dal menu di scelta rapida.  
  
11. Scegliere **Avvia debug** dal menu **Debug**.  
  
     `Form1` viene visualizzata.  
  
12. Fare clic su `valueButton1`.  
  
     Il numero "5" verrà visualizzato in `label1`, a significare che la proprietà `ButtonValue` del controllo ereditato è stata passata a `label1` mediante il metodo `valueButton1_Click`. Il controllo `ValueButton` erediterà tutte le funzionalità del pulsante standard per Windows Forms, ma esporrà una proprietà personalizzata aggiuntiva.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [Procedura dettagliata: Modifica di un controllo composito con Visual C#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
