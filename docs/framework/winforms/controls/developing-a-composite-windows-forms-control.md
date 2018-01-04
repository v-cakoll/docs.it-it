---
title: Sviluppo di un controllo Windows Form composto
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b98ba10e1c865417b9e844c4d5c31334f763e1b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="developing-a-composite-windows-forms-control"></a>Sviluppo di un controllo Windows Form composto
È possibile sviluppare un controllo Windows Form composito combinando altri controlli Windows Form. I controlli compositi che derivano da <xref:System.Web.UI.UserControl> sono denominati controlli utente. La classe base, <xref:System.Windows.Forms.UserControl>, fornisce il routing della tastiera per i controlli figlio, garantendo così che i controlli figlio possano ricevere lo stato attivo. Per un esempio di un controllo utente, vedere il <xref:System.Windows.Forms.UserControl> sample in [procedura: applicare attributi nei controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
 La finestra di progettazione di Windows Form in [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] fornisce supporto avanzato in fase di progettazione per la creazione di controlli utente.  
  
-   [Procedura: Visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))  
  
-   [Procedura dettagliata: Serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))  
  
-   [Procedura dettagliata: Eredità da un controllo Windows Form con Visual C#](http://msdn.microsoft.com/en-us/09476da0-8d4c-4a4c-b969-649519dfb438)  
  
-   [Procedura: Specificare una bitmap nella casella degli strumenti per un controllo](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))  
  
-   [Procedura: ereditare da controlli Windows Form esistenti](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))  
  
-   [Procedura dettagliata: Debug di controlli Windows Form personalizzati in fase di progettazione](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))  
  
-   [Procedura: ereditare dalla classe Control](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))  
  
-   [Procedura: eseguire il test del comportamento in fase di esecuzione di UserControl](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))  
  
-   [Procedura: allineare un controllo ai bordi dei form in fase di progettazione](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))  
  
-   [Procedura: ereditare dalla classe UserControl](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))  
  
-   [Procedura: creare controlli per Windows Form](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))  
  
-   [Procedura: modificare controlli compositi](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))  
  
-   [Procedura dettagliata: Modifica di un controllo composito con Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))  
  
-   [Procedura dettagliata: Modifica di un controllo composito con Visual C#](http://msdn.microsoft.com/en-us/f88481a8-c746-4a36-9479-374ce5f2e91f)  
  
-   [Procedura dettagliata: Eredità da un controllo Windows Form con Visual Basic](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))  
  
-   [Procedura: Creare un controllo di Windows Form che sfrutta le funzionalità di progettazione](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))  
  
-   [Procedura: Creare un controllo Windows Form che utilizza le funzionalità di progettazione](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Applicare attributi nei controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)  
 [Sviluppo di controlli Windows Form personalizzati con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Tipi di controlli personalizzati](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
