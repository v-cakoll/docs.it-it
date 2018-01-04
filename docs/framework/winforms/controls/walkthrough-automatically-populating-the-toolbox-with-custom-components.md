---
title: 'Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 08cb39215ea1d9aff1cd7ecc125bd731f14a4d7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati
Se i componenti sono definiti da un progetto nella soluzione attualmente aperta, verrà automaticamente visualizzato nel **della casella degli strumenti**, senza interventi da parte dell'utente. È anche possibile inserire manualmente il **della casella degli strumenti** con componenti personalizzati usando il [Scegli elementi della finestra della casella (Visual Studio)](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb), ma la **della casella degli strumenti** tiene conto elementi della soluzione di output con le seguenti caratteristiche di compilazione:  
  
-   Implementa <xref:System.ComponentModel.IComponent>;  
  
-   Non dispone <xref:System.ComponentModel.ToolboxItemAttribute> impostato su `false`;  
  
-   Non dispone <xref:System.ComponentModel.DesignTimeVisibleAttribute> impostato su `false`.  
  
> [!NOTE]
>  Il **della casella degli strumenti** segue le catene di riferimento, quindi non visualizzerà gli elementi che non vengono compilati da un progetto nella soluzione.  
  
 Questa procedura dettagliata illustra come un componente personalizzato viene automaticamente visualizzata nel **della casella degli strumenti** una volta creato il componente. Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione di un progetto Windows Form.  
  
-   Creazione di un componente personalizzato.  
  
-   Creazione di un'istanza di un componente personalizzato.  
  
-   Scaricare e ricaricare un componente personalizzato.  
  
 Al termine, si noterà che il **della casella degli strumenti** viene popolato con un componente che è stato creato.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio indica come creare il progetto e impostare il modulo.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1.  Creare un progetto di applicazione basata su Windows chiamato `ToolboxExample`.  
  
     Per altre informazioni, vedere [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Aggiungere un nuovo componente al progetto. Chiamarlo `DemoComponent`.  
  
     Per ulteriori informazioni, vedere [NIB: procedura: aggiungere nuovi elementi di progetto](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  
  
3.  Compilare il progetto.  
  
4.  Dal **strumenti** menu, fare clic su di **opzioni** elemento. Fare clic su **generale** sotto il **Progettazione Windows Form** e verificare che il **AutoToolboxPopulate** opzione è impostata su **True**.  
  
## <a name="creating-an-instance-of-a-custom-component"></a>Creazione di un'istanza di un componente personalizzato  
 Il passaggio successivo consiste nel creare un'istanza del componente personalizzato nel modulo. Poiché il **della casella degli strumenti** automaticamente gli account per il nuovo componente, il codice è semplice come la creazione di qualsiasi altro componente o controllo.  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a>Per creare un'istanza di un componente personalizzato  
  
1.  Aprire il form del progetto nel **progettazione form**.  
  
2.  Nel **della casella degli strumenti**, fare clic sulla scheda nuovo chiamata **Componenti ToolboxExample**.  
  
     Dopo aver selezionato la scheda, verrà visualizzato **DemoComponent**.  
  
    > [!NOTE]
    >  Per motivi di prestazioni, i componenti nell'area di popolati automaticamente il **della casella degli strumenti** non visualizzano le bitmap personalizzate e <xref:System.Drawing.ToolboxBitmapAttribute> non è supportata. Per visualizzare un'icona per un componente personalizzato nel **della casella degli strumenti**, utilizzare il **Scegli elementi della casella degli strumenti** finestra di dialogo per caricare il componente.  
  
3.  Trascinare il componente al form.  
  
     Viene aggiunta a un'istanza del componente di **sulla barra dei componenti**.  
  
## <a name="unloading-and-reloading-a-custom-component"></a>Scaricare e ricaricare un componente personalizzato  
 Il **della casella degli strumenti** tengano conto dei componenti in ogni progetto di caricamento e quando un progetto viene scaricato, rimuove i riferimenti ai componenti del progetto.  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a>Per sperimentare l'effetto della casella degli strumenti di scaricare e ricaricare i componenti  
  
1.  Scaricare il progetto dalla soluzione.  
  
     Per ulteriori informazioni sullo scaricamento dei progetti, vedere [NIB: procedura: scaricare e ricaricare i progetti](http://msdn.microsoft.com/en-us/abc0155b-8fcb-4ffc-95b6-698518a7100b). Se viene chiesto di salvare, scegliere **Sì**.  
  
2.  Aggiungere un nuovo **applicazione Windows** progetto alla soluzione. Aprire il form nel **progettazione**.  
  
     Il **Componenti ToolboxExample** scheda dal progetto precedente è stata rimossa.  
  
3.  Ricarica il `ToolboxExample` progetto.  
  
     Il **Componenti ToolboxExample** scheda ora viene visualizzato nuovamente.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa procedura dettagliata viene dimostrato che la **della casella degli strumenti** tiene conto dei componenti di un progetto, ma la **della casella degli strumenti** è anche dei controlli. Sperimentare controlli personalizzati aggiungendo e rimuovendo i progetti di controllo dalla soluzione.  
  
## <a name="see-also"></a>Vedere anche  
 [Generale, finestra di progettazione Windows Form, la finestra di dialogo Opzioni](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834)  
 [Procedura: modificare le schede della Casella degli strumenti](http://msdn.microsoft.com/en-us/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [Inserimento di controlli in Windows Form](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
