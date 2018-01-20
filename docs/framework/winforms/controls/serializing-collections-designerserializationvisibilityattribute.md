---
title: 'Procedura dettagliata: serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0267020f7e7a52e92b05a0bda0ee397e5c3393fc
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a>Procedura dettagliata: serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute
I controlli personalizzati talvolta espongono un insieme come una proprietà. Questa procedura dettagliata viene illustrato come utilizzare la <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> classe per controllare la modalità di serializzazione di una raccolta in fase di progettazione. L'applicazione di <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valore alla proprietà della raccolta assicura che la proprietà sarà serializzata.  
  
 Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: serializzare le raccolte di tipi Standard DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Disporre di autorizzazioni sufficienti creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a>Creazione di un controllo che contiene una raccolta serializzabile  
 Il primo passaggio consiste nel creare un controllo che contiene una raccolta serializzabile come una proprietà. È possibile modificare il contenuto di questa raccolta tramite il **Editor della raccolta**, che è possibile accedere dal **proprietà** finestra.  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a>Per creare un controllo con una raccolta serializzabile  
  
1.  Creare un progetto libreria di controlli Windows denominato `SerializationDemoControlLib`. Per ulteriori informazioni, vedere [modello libreria di controlli Windows](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Rinominare `UserControl1` a `SerializationDemoControl`. Per ulteriori informazioni, vedere [procedura: rinominare gli identificatori](http://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724).  
  
3.  Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> proprietà `10`.  
  
4.  Sul posto un <xref:System.Windows.Forms.TextBox> controllo il `SerializationDemoControl`.  
  
5.  Selezionare il controllo <xref:System.Windows.Forms.TextBox>. Nel **proprietà** finestra, impostare le proprietà seguenti.  
  
    |Proprietà|Modificare in|  
    |--------------|---------------|  
    |**Multiline**|`true`|  
    |**Ancoraggio**|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |**Barre di scorrimento**|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |**ReadOnly**|`true`|  
  
6.  Nel **Editor di codice**, dichiarare un campo di matrice di stringa denominato `stringsValue` in `SerializationDemoControl`.  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  Definire il `Strings` proprietà il `SerializationDemoControl`.  
  
> [!NOTE]
>  Il <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valore viene utilizzato per attivare la serializzazione della raccolta.  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  Per compilare il progetto ed eseguire il controllo in **UserControl Test Container**, premere F5.  
  
2.  Trovare il `Strings` proprietà il <xref:System.Windows.Forms.PropertyGrid> del **UserControl Test Container**. Fare clic su di `Strings` proprietà, quindi fare clic sui puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) per aprire il **Editor raccolta di stringhe**.  
  
3.  Immettere più stringhe nel **Editor raccolta di stringhe**. È necessario separarli premendo INVIO alla fine di ogni stringa. Fare clic su **OK** dopo aver terminato le stringhe.  
  
> [!NOTE]
>  Vengono visualizzate le stringhe immesse nel <xref:System.Windows.Forms.TextBox> del `SerializationDemoControl`.  
  
## <a name="serializing-a-collection-property"></a>La serializzazione di una proprietà di raccolta  
 Per testare il comportamento di serializzazione del controllo, verrà posizionato in un form e modificare il contenuto della raccolta con il **Editor della raccolta**. È possibile osservare lo stato di raccolta serializzata in un file speciale della finestra di progettazione, in cui il **Progettazione Windows Form** genera codice.  
  
#### <a name="to-serialize-a-collection"></a>Per serializzare una raccolta  
  
1.  Aggiungere un progetto applicazione Windows alla soluzione. Denominare il progetto `SerializationDemoControlTest`.  
  
2.  Nel **della casella degli strumenti**, individuare la scheda **Componenti SerializationDemoControlLib**. In questa scheda, si trova il `SerializationDemoControl`. Per altre informazioni, vedere [Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
3.  Sul posto un `SerializationDemoControl` sul form.  
  
4.  Trovare il `Strings` proprietà il **proprietà** finestra. Fare clic su di `Strings` proprietà, quindi fare clic sui puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) per aprire il **Editor raccolta di stringhe**.  
  
5.  Digitare diverse stringhe nel **Editor raccolta di stringhe**. È necessario separarli premendo INVIO alla fine di ogni stringa. Fare clic su **OK** dopo aver terminato le stringhe.  
  
> [!NOTE]
>  Vengono visualizzate le stringhe immesse nel <xref:System.Windows.Forms.TextBox> del `SerializationDemoControl`.  
  
1.  In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.  
  
2.  Aprire il **Form1** nodo. In cui è presente un file denominato **Form1. Designer.cs** o **Form1**. Si tratta del file in cui il **Progettazione Windows Form** genera codice che rappresenta lo stato in fase di progettazione del form e i relativi controlli figlio. Aprire il file nell'**editor di codice**.  
  
3.  Aprire l'area denominata **codice generato da Progettazione Windows Form** e individuare la sezione **serializationDemoControl1**. Sotto l'etichetta è il codice che rappresenta lo stato serializzato del controllo. Le stringhe digitato nel passaggio 5 vengono visualizzate in un'assegnazione di `Strings` proprietà. Gli esempi di codice seguente in c# e Visual Basic, Mostra codice simile a ciò che viene visualizzato se digitato le stringhe "rosso", "arancione" e "giallo".  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  Nel **Editor di codice**, modificare il valore della <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> sul `Strings` proprietà <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. Ricompilare la soluzione e ripetere i passaggi 3 e 4.  
  
> [!NOTE]
>  In questo caso, il **Progettazione Windows Form** alcuna assegnazione genera la `Strings` proprietà.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Una volta che in grado di serializzare una raccolta di tipi standard, è consigliabile integrare in modo più specifico i controlli personalizzati nell'ambiente di progettazione. Gli argomenti seguenti viene descritto come migliorare l'integrazione in fase di progettazione di controlli personalizzati:  
  
-   [Architettura della fase di progettazione](http://msdn.microsoft.com/library/4881917b-628f-4689-b872-472e4f8a4e3a)  
  
-   [Attributi nei controlli Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [Panoramica di serializzazione della finestra di progettazione](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
  
-   [Procedura dettagliata: Creazione di un controllo Windows Form che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>  
 [Panoramica di serializzazione della finestra di progettazione](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
 [Procedura: serializzare le raccolte di tipi Standard tramite DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)  
 [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
