---
title: Utilizzo di controlli WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e9883e9d31fc9e3e2ec3ca06b4fc830bcdc338ae
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460689"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Usare i controlli WPF nelle app Windows Forms

È possibile utilizzare i controlli Windows Presentation Foundation (WPF) nelle applicazioni basate su Windows Forms. Sebbene si tratta di due tecnologie di visualizzazione diverse, interagiscono senza problemi.

Il Progettazione Windows Form in Visual Studio fornisce un ambiente di progettazione visiva per l'hosting di controlli Windows Presentation Foundation. Un controllo WPF è ospitato da un controllo Windows Forms speciale denominato <xref:System.Windows.Forms.Integration.ElementHost>. Questo controllo consente al controllo WPF di partecipare al layout del form e di ricevere i messaggi della tastiera e del mouse. In fase di progettazione è possibile disporre il controllo <xref:System.Windows.Forms.Integration.ElementHost> come qualsiasi Windows Forms controllo.

È inoltre possibile utilizzare Windows Forms controlli nelle applicazioni basate su WPF. Per altre informazioni, vedere [progettazione di XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

## <a name="see-also"></a>Vedere anche

- [Interoperatività di WPF e Windows Forms](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
