---
title: 'Procedura: Copiare e incollare un controllo ElementHost in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 0f3367deaaec04744a3f812d7f2d08047d7eb588
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211375"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a>Procedura: Copiare e incollare un controllo ElementHost in fase di progettazione

Questa procedura illustra come copiare un controllo Windows Presentation Foundation (WPF) in un Windows Form in Visual Studio.

## <a name="copy-and-paste-an-elementhost-control-at-design-time"></a>Copiare e incollare un controllo ElementHost in fase di progettazione

1. Aggiungere un nuovo controllo WPF <xref:System.Windows.Controls.UserControl> al progetto Windows Form. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per altre informazioni, vedere [Procedura dettagliata: Creare nuovo contenuto WPF in Windows Form in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà di `UserControl1` per `200`.

3. Impostare il valore della proprietà <xref:System.Windows.Controls.Control.Background%2A> su `Blue`.

4. Compilare il progetto.

5. Aprire `Form1` in Progettazione Windows Form.

6. Dal **casella degli strumenti**, trascinare un'istanza di `UserControl1` nel form.

   L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.

7. Con `elementHost1` selezionato, premere CTRL+C per copiarlo negli Appunti.

8. Premere CTRL + V per incollare il controllo copiato nel form.

   Una nuova <xref:System.Windows.Forms.Integration.ElementHost> controllo denominato `elementHost2` viene creato nel form.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migrazione e interoperabilità](../../wpf/advanced/migration-and-interoperability.md)
- [Uso di controlli WPF](using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
