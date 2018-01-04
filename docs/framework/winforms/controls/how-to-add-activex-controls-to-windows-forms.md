---
title: 'Procedura: aggiungere i controlli ActiveX a Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9328400917208dde9f81b493fbf26c6080dc9c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Procedura: aggiungere i controlli ActiveX a Windows Form
Durante la progettazione Windows Form è ottimizzato per ospitare controlli Windows Form, è anche possibile inserire controlli ActiveX in Windows Form.  
  
> [!CAUTION]
>  Quando i controlli ActiveX aggiunti, esistono limitazioni relative alle prestazioni per Windows Form.  
  
 Prima di aggiungere al form controlli ActiveX, è necessario aggiungere alla casella degli strumenti. Per ulteriori informazioni, vedere [componenti COM, finestra di dialogo Personalizza casella degli strumenti](http://msdn.microsoft.com/en-us/171333f3-f207-4e02-bbdc-17862556212c).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>Per aggiungere un controllo ActiveX a Windows Form  
  
-   Fare doppio clic sul controllo della casella degli strumenti.  
  
     [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]Aggiunge tutti i riferimenti al controllo del progetto. Per ulteriori informazioni sugli aspetti da tenere presenti quando si utilizzano controlli ActiveX in Windows Form, vedere [considerazioni quando si ospita un controllo ActiveX in un Windows Form](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  Windows Forms ActiveX Control Importer (AxImp.exe) crea argomenti dell'evento di un tipo diverso da quanto previsto durante l'importazione di librerie a collegamento dinamico ActiveX. Gli argomenti creati da AxImp.exe sono simili al seguente: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, quando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` è previsto. Tenere presente che questa anomalia impedisce al codice funziona correttamente. Per informazioni dettagliate, vedere [utilità di importazione di controllo ActiveX di Windows Form (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)  
 [Confronto tra controlli e oggetti programmabili in diversi linguaggi e librerie](http://msdn.microsoft.com/en-us/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [Procedura: Aggiungere controlli a un Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Disposizione di controlli in Windows Form](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Controlli Windows Form per funzione](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
