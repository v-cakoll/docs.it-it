---
title: 'Procedura: specificare una bitmap nella casella degli strumenti per un controllo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 61f60aaeab904dff80408a1dc46c2882fb5e22b9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458319"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>Procedura: specificare una bitmap nella casella degli strumenti per un controllo

Se si vuole che venga visualizzata un'icona speciale per il controllo nella **casella degli strumenti** di Visual Studio, è possibile specificare una particolare immagine usando il <xref:System.Drawing.ToolboxBitmapAttribute>. Questa classe è un *attributo*, un tipo speciale di classe che è possibile allegare ad altre classi. Per ulteriori informazioni sugli attributi, vedere [Cenni preliminari sugli attributi (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) per Visual Basic o [attributiC#()](../../../csharp/programming-guide/concepts/attributes/index.md) per. C#

Utilizzando la <xref:System.Drawing.ToolboxBitmapAttribute>, è possibile specificare una stringa che indica il percorso e il nome del file per una bitmap di 16 per 16 pixel. Questa bitmap viene quindi visualizzata accanto al controllo quando è aggiunta alla **Casella degli strumenti**. È anche possibile specificare un <xref:System.Type>. in questo caso, viene caricata la bitmap associata a tale tipo. Se si specifica sia un <xref:System.Type> che una stringa, il controllo Cerca una risorsa immagine con il nome specificato dal parametro stringa nell'assembly contenente il tipo specificato dal parametro <xref:System.Type>.

## <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>Per specificare una bitmap della casella degli strumenti per il controllo

1. Aggiungere la <xref:System.Drawing.ToolboxBitmapAttribute> alla dichiarazione di classe del controllo prima della parola chiave `Class` per Visual Basic e sopra la dichiarazione di classe per Visual C#.

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
    > La bitmap non viene visualizzata nella casella degli strumenti per i controlli e i componenti generati automaticamente. Per visualizzare la bitmap, ricaricare il controllo usando la finestra di dialogo **Scegli elementi della casella degli strumenti**. Per altre informazioni, vedere [Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
- [Panoramica degli attributi (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Attributi (C#)](../../../csharp/programming-guide/concepts/attributes/index.md)
