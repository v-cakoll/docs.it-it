---
title: Come aggiungere una schermata iniziale
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 39f53e21c40f036c65894b4f275cd5fb414999be
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740453"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>Procedura: aggiungere una schermata iniziale in un'applicazione WPF

In questo argomento viene illustrato come aggiungere una finestra di avvio o una *schermata iniziale*a un'applicazione Windows Presentation Foundation (WPF).

## <a name="to-add-an-existing-image-as-a-splash-screen"></a>Per aggiungere un'immagine esistente come schermata iniziale

1. Creare o trovare un'immagine che si vuole usare per la schermata iniziale. È possibile utilizzare qualsiasi formato di immagine supportato da Windows Imaging Component (WIC). Ad esempio, è possibile usare il formato BMP, GIF, JPEG, PNG o TIFF.

2. Aggiungere il file di immagine al progetto di applicazione WPF.

3. In **Esplora soluzioni**selezionare l'immagine.

4. Nella Finestra Proprietà fare clic sulla freccia a discesa relativa alla proprietà **azione di compilazione** .

5. Selezionare **SplashScreen** dall'elenco a discesa.

6. Premere **F5** per compilare ed eseguire l'applicazione.

     L'immagine della schermata iniziale viene visualizzata al centro dello schermo, quindi si dissolve quando viene visualizzata la finestra principale dell'applicazione.

## <a name="to-exclude-the-splash-screen-from-build"></a>Per escludere la schermata iniziale dalla compilazione

1. In **Esplora soluzioni**selezionare l'immagine della schermata iniziale.

2. Nella finestra **Proprietà** impostare l'azione di **compilazione** su **nessuno**.

## <a name="to-remove-the-splash-screen-from-an-application"></a>Per rimuovere la schermata iniziale da un'applicazione

In **Esplora soluzioni**eliminare l'immagine della schermata iniziale.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.SplashScreen>
- [Procedura: aggiungere elementi esistenti a un progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
