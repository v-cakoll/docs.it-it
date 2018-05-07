---
title: 'Procedura: sviluppare un controllo di Windows Form semplice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: 04cedc0df60ef95acb79b651ddcbcbb34ae5e920
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a>Procedura: sviluppare un controllo di Windows Form semplice
Questa sezione illustra i passaggi chiave per la creazione di un controllo di Windows Form personalizzato. Il controllo semplice sviluppato in questa procedura dettagliata consente l'allineamento della relativa <xref:System.Windows.Forms.Control.Text%2A> proprietà da modificare. Non genera o gestisce eventi.  
  
### <a name="to-create-a-simple-custom-control"></a>Per creare un controllo personalizzato semplice  
  
1.  Definire una classe che deriva da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
    ```vb  
    Public Class FirstControl  
       Inherits Control  
  
    End Class  
    ```  
  
    ```csharp  
    public class FirstControl:Control{}  
    ```  
  
2.  Definire le proprietà. (Non è necessario per definire le proprietà, poiché un controllo eredita le proprietà molti la <xref:System.Windows.Forms.Control> classe, ma la maggior parte dei controlli personalizzati in genere definite proprietà aggiuntive.) Frammento di codice seguente definisce una proprietà denominata `TextAlignment` che `FirstControl` viene utilizzata per formattare la visualizzazione del <xref:System.Windows.Forms.Control.Text%2A> proprietà ereditata da <xref:System.Windows.Forms.Control>. Per altre informazioni sulla definizione delle proprietà, vedere [Panoramica delle proprietà](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]  
  
     Quando si imposta una proprietà che modifica la visualizzazione del controllo, è necessario richiamare il <xref:System.Windows.Forms.Control.Invalidate%2A> metodo per ridisegnare il controllo. <xref:System.Windows.Forms.Control.Invalidate%2A> è definito nella classe base <xref:System.Windows.Forms.Control>.  
  
3.  Eseguire l'override protetto <xref:System.Windows.Forms.Control.OnPaint%2A> metodo ereditato da <xref:System.Windows.Forms.Control> per fornire la logica di rendering del controllo. Se esegue l'override <xref:System.Windows.Forms.Control.OnPaint%2A>, il controllo non sarà in grado di disegno. Nel frammento di codice seguente, il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo visualizza il <xref:System.Windows.Forms.Control.Text%2A> proprietà ereditata da <xref:System.Windows.Forms.Control> con l'allineamento specificato il `alignmentValue` campo.  
  
     [!code-csharp[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]  
  
4.  Specificare attributi per il controllo. Gli attributi attivano una finestra di progettazione per visualizzare correttamente il controllo e le relative proprietà ed eventi in fase di progettazione. Il seguente frammento di codice applica attributi alla proprietà `TextAlignment`. Nella finestra di progettazione, ad esempio Visual Studio, il <xref:System.ComponentModel.CategoryAttribute.Category%2A> attributo (mostrato nel frammento di codice), la proprietà da visualizzare in una categoria logica. Il <xref:System.ComponentModel.DescriptionAttribute.Description%2A> attributo determina una stringa descrittiva da visualizzare nella parte inferiore del **proprietà** finestra quando il `TextAlignment` proprietà è selezionata. Per altre informazioni sugli attributi, vedere [Attributi per componenti in fase di progettazione](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3).  
  
     [!code-csharp[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]  
  
5.  (facoltativo) Specifica risorse per il controllo. È possibile specificare una risorsa, ad esempio un'immagine bitmap, per il controllo tramite un'opzione del compilatore (`/res` per C#) per creare pacchetti di risorse con il controllo. In fase di esecuzione, è possibile recuperare la risorsa utilizzando i metodi della <xref:System.Resources.ResourceManager> classe. Per altre informazioni sulla creazione e sull'uso di risorse, vedere [Risorse nelle applicazioni desktop](../../../../docs/framework/resources/index.md).  
  
6.  Compilare e distribuire il controllo. Per compilare e distribuire `FirstControl,`, seguire i passaggi seguenti:  
  
    1.  Salvare il codice dell'esempio seguente in un file di origine, ad esempio FirstControl.cs o FirstControl.vb.  
  
    2.  Compilare il codice sorgente in un assembly e salvarlo nella directory dell'applicazione. Per questo scopo, eseguire il comando seguente dalla directory che contiene il file d'origine.  
  
        ```console  
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb  
        ```  
  
        ```console 
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs  
        ```  
  
         L'opzione `/t:library` indica al compilatore che l'assembly che si sta creando è una libreria e non un file eseguibile. L'opzione `/out` specifica il percorso e il nome dell'assembly. L'opzione `/r` specifica il nome delle assembly a cui fa riferimento il codice. In questo esempio, si crea un assembly privato che può essere usato solo dalle applicazioni. Di conseguenza, è necessario salvarlo nella directory dell'applicazione. Per altre informazioni sulla creazione di pacchetti e sulla distribuzione di un controllo, vedere [Distribuzione](../../../../docs/framework/deployment/index.md).  
  
 L'esempio seguente visualizza il codice per `FirstControl`. Il controllo è incluso nello spazio dei nomi `CustomWinControls`. Uno spazio dei nomi specifica un raggruppamento logico di tipi correlati. È possibile creare il controllo in uno spazio dei nomi nuovo o esistente. In C#, la dichiarazione `using` (in Visual Basic, `Imports`) consente di accedere ai tipi da uno spazio dei nomi senza usare il nome completo del tipo. Nell'esempio seguente, il `using` dichiarazione consente al codice accedere alla classe <xref:System.Windows.Forms.Control> da <xref:System.Windows.Forms?displayProperty=nameWithType> semplicemente come <xref:System.Windows.Forms.Control> anziché utilizzare il nome completo <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
 [!code-csharp[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
 [!code-vb[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]  
  
## <a name="using-the-custom-control-on-a-form"></a>Uso del controllo personalizzato in un Form  
 L'esempio seguente illustra un form semplice che usa `FirstControl`. Crea tre istanze di `FirstControl`, ognuno con un valore diverso per la proprietà `TextAlignment`.  
  
#### <a name="to-compile-and-run-this-sample"></a>Per compilare ed eseguire l'esempio  
  
1.  Salvare il codice dell'esempio seguente in un file di origine (SimpleForm.cs o SimpleForms.vb).  
  
2.  Compilare il codice sorgente in un assembly eseguibile tramite il comando seguente dalla directory che contiene il file di origine.  
  
    ```console  
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb  
    ```  
  
    ```console 
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs  
    ```  
  
     CustomWinControls. dll è l'assembly che contiene la classe `FirstControl`. L'assembly deve essere nella stessa directory del file di origine per il form che accede all'assembly (SimpleForm.cs o SimpleForms.vb).  
  
3.  Eseguire SimpleForm.exe usando il comando seguente.  
  
    ```console
    SimpleForm  
    ```  
  
 [!code-csharp[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
 [!code-vb[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]  
  
## <a name="see-also"></a>Vedere anche  
 [Proprietà dei controlli Windows Form](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [Eventi dei controlli di Windows Form](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)
