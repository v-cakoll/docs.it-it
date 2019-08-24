---
title: 'Procedura: Specificare una bitmap nella casella degli strumenti per un controllo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e6da7318ba481af721a9220c8f71af2a18e764a3
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015782"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>Procedura: Specificare una bitmap nella casella degli strumenti per un controllo

Se si vuole che venga visualizzata un'icona speciale per il controllo nella **casella degli strumenti** di Visual Studio, è possibile specificare una particolare immagine usando <xref:System.Drawing.ToolboxBitmapAttribute>. Questa classe è un *attributo*, un tipo speciale di classe che è possibile allegare ad altre classi. Per ulteriori informazioni sugli attributi, vedere [Cenni preliminari sugli attributi (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) per Visual Basic o [attributi (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) per. C#

Utilizzando la <xref:System.Drawing.ToolboxBitmapAttribute>, è possibile specificare una stringa che indica il percorso e il nome file per una bitmap di 16 per 16 pixel. Questa bitmap viene quindi visualizzata accanto al controllo quando è aggiunta alla **Casella degli strumenti**. È anche possibile specificare <xref:System.Type>, nel qual caso viene caricata la bitmap associata a tale tipo. Se si specificano sia <xref:System.Type> un oggetto che una stringa, il controllo Cerca una risorsa immagine con il nome specificato dal parametro stringa nell'assembly contenente il tipo specificato <xref:System.Type> dal parametro.

## <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>Per specificare una bitmap della casella degli strumenti per il controllo

1. Aggiungere alla dichiarazione di classe del controllo prima della `Class` parola chiave per Visual Basic e sopra la dichiarazione di classe per l'oggetto visivo. C# <xref:System.Drawing.ToolboxBitmapAttribute>

    ```vb
    ' Specifies the bitmap associated with the Button type.
    <ToolboxBitmap(GetType(Button))> Class MyControl1
    ' Specifies a bitmap file.
    End Class
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _
       Class MyControl2
    End Class
    ' Specifies a type that indicates the assembly to search, and the name
    ' of an image resource to look for.
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl
    End Class
    ```

    ```csharp
    // Specifies the bitmap associated with the Button type.
    [ToolboxBitmap(typeof(Button))]
    class MyControl1 : UserControl
    {
    }
    // Specifies a bitmap file.
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]
    class MyControl2 : UserControl
    {
    }
    // Specifies a type that indicates the assembly to search, and the name
    // of an image resource to look for.
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]
    class MyControl : UserControl
    {
    }
    ```

2. Ricompilare il progetto.

    > [!NOTE]
    > La bitmap non viene visualizzata nella casella degli strumenti per i controlli e i componenti generati automaticamente. Per visualizzare la bitmap, ricaricare il controllo usando la finestra di dialogo **Scegli elementi della casella degli strumenti**. Per altre informazioni, vedere [Procedura dettagliata: Popolamento automatico della casella degli strumenti con](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)componenti personalizzati.

## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [Procedura dettagliata: Popolamento automatico della casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
- [Panoramica degli attributi (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Attributi (C#)](../../../csharp/programming-guide/concepts/attributes/index.md)
