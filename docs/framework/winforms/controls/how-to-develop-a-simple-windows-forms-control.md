---
title: Sviluppare un controllo semplice
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: 5383cee5358dbd260fc6c023d3db607da6b10ea4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742260"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a>Procedura: sviluppare un controllo di Windows Form semplice

Questa sezione illustra i passaggi chiave per la creazione di un controllo di Windows Form personalizzato. Il controllo semplice sviluppato in questa procedura dettagliata consente di modificare l'allineamento della relativa proprietà <xref:System.Windows.Forms.Control.Text%2A>. Non genera o gestisce eventi.

### <a name="to-create-a-simple-custom-control"></a>Per creare un controllo personalizzato semplice

1. Definire una classe che deriva da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.

    ```vb
    Public Class FirstControl
       Inherits Control

    End Class
    ```

    ```csharp
    public class FirstControl:Control {}
    ```

2. Definire le proprietà. Non è necessario definire le proprietà perché un controllo eredita molte proprietà dalla classe <xref:System.Windows.Forms.Control>, ma la maggior parte dei controlli personalizzati in genere definiscono proprietà aggiuntive. Il frammento di codice seguente definisce una proprietà denominata `TextAlignment` utilizzata da `FirstControl` per formattare la visualizzazione della proprietà <xref:System.Windows.Forms.Control.Text%2A> ereditata da <xref:System.Windows.Forms.Control>. Per altre informazioni sulla definizione delle proprietà, vedere [Panoramica delle proprietà](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120)).

     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]

     Quando si imposta una proprietà che modifica la visualizzazione visiva del controllo, è necessario richiamare il metodo <xref:System.Windows.Forms.Control.Invalidate%2A> per ricreare il controllo. <xref:System.Windows.Forms.Control.Invalidate%2A> viene definito nella classe di base <xref:System.Windows.Forms.Control>.

3. Eseguire l'override del metodo <xref:System.Windows.Forms.Control.OnPaint%2A> protetto ereditato da <xref:System.Windows.Forms.Control> per fornire la logica di rendering al controllo. Se non si esegue l'override di <xref:System.Windows.Forms.Control.OnPaint%2A>, il controllo non sarà in grado di disegnarsi automaticamente. Nel frammento di codice seguente il metodo <xref:System.Windows.Forms.Control.OnPaint%2A> Visualizza la proprietà <xref:System.Windows.Forms.Control.Text%2A> ereditata da <xref:System.Windows.Forms.Control> con l'allineamento specificato dal campo `alignmentValue`.

     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]

4. Specificare attributi per il controllo. Gli attributi attivano una finestra di progettazione per visualizzare correttamente il controllo e le relative proprietà ed eventi in fase di progettazione. Il seguente frammento di codice applica attributi alla proprietà `TextAlignment`. In una finestra di progettazione, ad esempio Visual Studio, l'attributo <xref:System.ComponentModel.CategoryAttribute.Category%2A> (mostrato nel frammento di codice) fa sì che la proprietà venga visualizzata in una categoria logica. L'attributo <xref:System.ComponentModel.DescriptionAttribute.Description%2A> causa la visualizzazione di una stringa descrittiva nella parte inferiore della finestra **Proprietà** quando viene selezionata la proprietà `TextAlignment`. Per altre informazioni sugli attributi, vedere [Attributi per componenti in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).

     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]

5. (facoltativo) Specifica risorse per il controllo. È possibile specificare una risorsa, ad esempio un'immagine bitmap, per il controllo tramite un'opzione del compilatore (`/res` per C#) per creare pacchetti di risorse con il controllo. In fase di esecuzione, è possibile recuperare la risorsa usando i metodi della classe <xref:System.Resources.ResourceManager>. Per altre informazioni sulla creazione e sull'uso di risorse, vedere [Risorse nelle applicazioni desktop](../../resources/index.md).

6. Compilare e distribuire il controllo. Per compilare e distribuire `FirstControl,`, seguire i passaggi seguenti:

    1. Salvare il codice dell'esempio seguente in un file di origine, ad esempio FirstControl.cs o FirstControl.vb.

    2. Compilare il codice sorgente in un assembly e salvarlo nella directory dell'applicazione. Per questo scopo, eseguire il comando seguente dalla directory che contiene il file d'origine.

        ```console
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb
        ```

        ```console
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs
        ```

         L'opzione `/t:library` indica al compilatore che l'assembly che si sta creando è una libreria e non un file eseguibile. L'opzione `/out` specifica il percorso e il nome dell'assembly. L'opzione `/r` specifica il nome delle assembly a cui fa riferimento il codice. In questo esempio, si crea un assembly privato che può essere usato solo dalle applicazioni. Di conseguenza, è necessario salvarlo nella directory dell'applicazione. Per altre informazioni sulla creazione di pacchetti e sulla distribuzione di un controllo, vedere [Distribuzione](../../deployment/index.md).

L'esempio seguente visualizza il codice per `FirstControl`. Il controllo è incluso nello spazio dei nomi `CustomWinControls`. Uno spazio dei nomi specifica un raggruppamento logico di tipi correlati. È possibile creare il controllo in uno spazio dei nomi nuovo o esistente. In C#, la dichiarazione `using` (in Visual Basic, `Imports`) consente di accedere ai tipi da uno spazio dei nomi senza usare il nome completo del tipo. Nell'esempio seguente la dichiarazione di `using` consente al codice di accedere alla classe <xref:System.Windows.Forms.Control> da <xref:System.Windows.Forms?displayProperty=nameWithType> semplicemente <xref:System.Windows.Forms.Control> anziché dover usare il nome completo <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.

[!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
[!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]

## <a name="using-the-custom-control-on-a-form"></a>Uso del controllo personalizzato in un Form

L'esempio seguente illustra un form semplice che usa `FirstControl`. Crea tre istanze di `FirstControl`, ognuno con un valore diverso per la proprietà `TextAlignment`.

#### <a name="to-compile-and-run-this-sample"></a>Per compilare ed eseguire l'esempio

1. Salvare il codice dell'esempio seguente in un file di origine (SimpleForm.cs o SimpleForms.vb).

2. Compilare il codice sorgente in un assembly eseguibile tramite il comando seguente dalla directory che contiene il file di origine.

    ```console
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb
    ```

    ```console
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs
    ```

     CustomWinControls. dll è l'assembly che contiene la classe `FirstControl`. L'assembly deve essere nella stessa directory del file di origine per il form che accede all'assembly (SimpleForm.cs o SimpleForms.vb).

3. Eseguire SimpleForm.exe usando il comando seguente.

    ```console
    SimpleForm
    ```

[!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
[!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]

## <a name="see-also"></a>Vedere anche

- [Proprietà dei controlli Windows Form](properties-in-windows-forms-controls.md)
- [Eventi nei controlli di Windows Form](events-in-windows-forms-controls.md)
