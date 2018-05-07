---
title: "Procedura: aggiungere una schermata iniziale in un'applicazione WPF"
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 06d6cb7c5a5081d3b6c4979ab50e1caaa726acbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>Procedura: aggiungere una schermata iniziale in un'applicazione WPF
In questo argomento viene illustrato come aggiungere una finestra di avvio, o *schermata*, a un'applicazione Windows Presentation Foundation (WPF).  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a>Per aggiungere un'immagine esistente come schermata iniziale  
  
1.  Creare o trovare un'immagine che si desidera utilizzare per la schermata iniziale. È possibile utilizzare qualsiasi formato di immagine supportato da Windows Imaging Component (WIC). Ad esempio, è possibile utilizzare il formato TIFF, GIF, JPEG, PNG o BMP.  
  
2.  Aggiungere il file di immagine al progetto di applicazione WPF. Per ulteriori informazioni, vedere [NIB: procedura: aggiungere elementi esistenti a un progetto](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
3.  In Esplora soluzioni, selezionare l'immagine.  
  
4.  Nella finestra Proprietà fare clic sulla freccia giù per la **azione di compilazione** proprietà.  
  
5.  Selezionare **SplashScreen** dall'elenco a discesa.  
  
    > [!NOTE]
    >  Se non viene visualizzato il **SplashScreen** opzione, assicurarsi di controllare che si stia usando [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 o versione successiva.  
  
6.  Premere F5 per compilare ed eseguire l'applicazione.  
  
     L'immagine della schermata iniziale viene visualizzato al centro dello schermo e quindi scompare quando viene visualizzata la finestra principale dell'applicazione.  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>Per rimuovere la schermata da un'applicazione  
  
1.  In Esplora soluzioni, selezionare l'immagine della schermata iniziale.  
  
2.  Nella finestra Proprietà impostare il **azione di compilazione** a **Nessuno**.  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a>Per rimuovere la schermata da un'applicazione  
  
-   In Esplora soluzioni, eliminare l'immagine della schermata iniziale.  
  
-   Escludere l'immagine della schermata iniziale dal progetto.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.SplashScreen>  
 [NIB: procedura: aggiungere elementi esistenti a un progetto](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
