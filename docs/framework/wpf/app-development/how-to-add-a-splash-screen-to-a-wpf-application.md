---
title: "Procedura: Aggiunta di una schermata iniziale in un'applicazione WPF"
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 545fce07d0fab3dca8116f2cacfc068b62cbbde2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537543"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>Procedura: Aggiunta di una schermata iniziale in un'applicazione WPF

In questo argomento viene illustrato come aggiungere una finestra di avvio, oppure *schermata iniziale*, a un'applicazione Windows Presentation Foundation (WPF).

## <a name="to-add-an-existing-image-as-a-splash-screen"></a>Per aggiungere un'immagine esistente come schermata iniziale

1.  Creare o trovare un'immagine che si desidera utilizzare per la schermata iniziale. È possibile usare qualsiasi formato di immagine supportato da Windows Imaging Component (WIC). Ad esempio, è possibile utilizzare il formato TIFF, GIF, JPEG, PNG o BMP.

2.  Aggiungere il file di immagine al progetto di applicazione WPF.

3.  Nelle **Esplora soluzioni**, selezionare l'immagine.

4.  Nella finestra Proprietà, fare clic sulla freccia giù per il **azione di compilazione** proprietà.

5.  Selezionare **SplashScreen** nell'elenco a discesa.

6.  Premere **F5** per compilare ed eseguire l'applicazione.

     Immagine della schermata iniziale viene visualizzato al centro dello schermo e quindi scompare quando viene visualizzata la finestra principale dell'applicazione.

## <a name="to-exclude-the-splash-screen-from-build"></a>Per escludere la schermata iniziale di compilazione

1.  Nelle **Esplora soluzioni**, selezionare l'immagine della schermata iniziale.

2.  Nel **proprietà** impostare nella finestra di **azione di compilazione** a **None**.

## <a name="to-remove-the-splash-screen-from-an-application"></a>Per rimuovere la schermata da un'applicazione

Nelle **Esplora soluzioni**, eliminare l'immagine della schermata iniziale.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.SplashScreen>
- [Procedura: Aggiungere elementi esistenti a un progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
