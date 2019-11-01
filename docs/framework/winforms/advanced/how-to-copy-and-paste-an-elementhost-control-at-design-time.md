---
title: 'Procedura: copiare e incollare un controllo ElementHost in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3d1887eb1161f714962c2c26d6fe618749b26c0f
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197474"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a>Procedura: copiare e incollare un controllo ElementHost

Questa procedura illustra come copiare un controllo Windows Presentation Foundation (WPF) in un Windows Form in Visual Studio.

1. In Visual Studio aggiungere un nuovo <xref:System.Windows.Controls.UserControl> WPF a un progetto Windows Forms. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovi contenuti WPF in Windows Forms in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. Nella finestra **Proprietà** impostare il valore delle proprietà <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> di `UserControl1` su **200**.

3. Impostare il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> su **blu**.

4. Compilare il progetto.

5. Aprire `Form1` in Progettazione Windows Form.

6. Dalla **casella degli strumenti**trascinare un'istanza di `UserControl1` nel form.

   L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.

7. Con `elementHost1` selezionato, premere **Ctrl**+**C** per copiarlo negli Appunti.

8. Premere **Ctrl**+**V** per incollare il controllo copiato nel form.

   Nel form viene creato un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost2`.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migrazione e interoperabilità](../../wpf/advanced/migration-and-interoperability.md)
- [Uso di controlli WPF](using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
