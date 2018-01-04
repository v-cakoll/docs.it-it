---
title: 'Procedura dettagliata: copiare e incollare un controllo ElementHost in Windows Form separati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 579bce312296d9799f9f7c739f740e2c9111ccff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a>Procedura dettagliata: copiare e incollare un controllo ElementHost in Windows Form separati
Questa procedura dettagliata mostra come copiare un controllo Windows Presentation Foundation (WPF) da un Windows Form a un altro.  
  
 Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:  
  
-   Creare il progetto.  
  
-   Copiare un controllo WPF.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto Windows Form.  
  
> [!NOTE]
>  Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
-   Creare un nuovo progetto applicazione Windows Forms in Visual Basic o Visual c# denominato `CopyElementHost`.  
  
## <a name="copying-a-wpf-control"></a>Copia di un controllo WPF  
 Dopo aver aggiunto un controllo WPF al progetto, è possibile copiarlo in altri form del progetto.  
  
#### <a name="to-copy-a-wpf-control"></a>Per copiare un controllo WPF  
  
1.  Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Compilare il progetto.  
  
3.  Aprire `Form1` in Progettazione Windows Form.  
  
4.  Dal **della casella degli strumenti**, trascinare un'istanza di `UserControl1` nel form.  
  
     L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.  
  
5.  Con `elementHost1` selezionato, premere CTRL+C per copiarlo negli Appunti.  
  
6.  Aggiungere un nuovo Windows Form al progetto. Usare il nome predefinito per il tipo di form, `Form2`.  
  
7.  Con `Form2` aperto in Progettazione Windows Form, premere CTRL+V per incollare una copia di `elementHost1` nel form.  
  
     Anche il controllo copiato viene denominato `elementHost1`, perché è un campo privato della classe `Form2`. Non esiste alcun conflitto di nomi con `elementHost1` della classe `Form1`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Migrazione e interoperabilità](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Uso di controlli WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [WPF Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
