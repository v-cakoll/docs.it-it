---
title: 'Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 488d51e748ea17b09e61b982db7abadc34f8e311
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43671891"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati
Se i componenti vengono definiti da un progetto nella soluzione attualmente aperta, verranno automaticamente visualizzati nei **casella degli strumenti**, senza alcun intervento da parte dell'utente. È anche possibile inserire manualmente il **casella degli strumenti** con i componenti personalizzati usando la [Scegli elementi della finestra della casella (Visual Studio)](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb), ma il **della casella degli strumenti** tengano conto elementi della soluzione di output con tutte le caratteristiche seguenti di compilazione:  
  
-   Implementa <xref:System.ComponentModel.IComponent>;  
  
-   Non dispone <xref:System.ComponentModel.ToolboxItemAttribute> impostato su `false`;  
  
-   Non dispone <xref:System.ComponentModel.DesignTimeVisibleAttribute> impostato su `false`.  
  
> [!NOTE]
>  Il **casella degli strumenti** non rispetta le catene di riferimento, in modo da non visualizzerà gli elementi che non vengono compilati da un progetto nella soluzione.  
  
 Questa procedura dettagliata illustra come un componente personalizzato viene visualizzato automaticamente nel **casella degli strumenti** dopo aver compilato il componente. Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione di un progetto Windows Form.  
  
-   Creazione di un componente personalizzato.  
  
-   Creazione di un'istanza di un componente personalizzato.  
  
-   Scaricare e ricaricare un componente personalizzato.  
  
 Al termine, si noterà che il **casella degli strumenti** viene popolato con un componente che è stato creato.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio indica come creare il progetto e impostare il modulo.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1.  Creare un progetto di applicazione basata su Windows denominato `ToolboxExample` (**File** > **New** > **progetto**  >  **Visual c#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).  
  
2.  Aggiungere un nuovo componente al progetto. Chiamarlo `DemoComponent`.  
  
     Per altre informazioni, vedere [NIB: procedura: aggiungere nuovi elementi di progetto](https://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  
  
3.  Compilare il progetto.  
  
4.  Dal **degli strumenti** menu, fare clic sul **opzioni** elemento. Fare clic su **generali** sotto il **progettazione di Windows Form** e verificare che il **AutoToolboxPopulate** opzione è impostata su **True**.  
  
## <a name="creating-an-instance-of-a-custom-component"></a>Creazione di un'istanza di un componente personalizzato  
 Il passaggio successivo consiste nel creare un'istanza del componente personalizzato nel modulo. Poiché il **casella degli strumenti** automaticamente gli account per il nuovo componente, è semplice come la creazione di qualsiasi altro componente o controllo.  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a>Per creare un'istanza di un componente personalizzato  
  
1.  Aprire il form del progetto nel **progettazione form**.  
  
2.  Nel **casella degli strumenti**, fare clic sulla scheda nuovo chiamata **Componenti ToolboxExample**.  
  
     Dopo aver selezionato la scheda, si noterà **DemoComponent**.  
  
    > [!NOTE]
    >  Per motivi di prestazioni, i componenti nell'area popolato automaticamente della **casella degli strumenti** non vengono visualizzate le bitmap personalizzate e <xref:System.Drawing.ToolboxBitmapAttribute> non è supportato. Per visualizzare un'icona per un componente personalizzato nella **casella degli strumenti**, utilizzare il **Scegli elementi della casella degli strumenti** finestra di dialogo per caricare il componente.  
  
3.  Trascinare il componente al form.  
  
     Viene creata e aggiunto a un'istanza del componente di **sulla barra dei componenti**.  
  
## <a name="unloading-and-reloading-a-custom-component"></a>Scaricare e ricaricare un componente personalizzato  
 Il **casella degli strumenti** tengano conto dei componenti in ogni progetto di caricamento e quando viene scaricato un progetto, vengono rimossi i riferimenti ai componenti del progetto.  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a>Per sperimentare l'effetto della casella degli strumenti di scaricamento e il ricaricamento di componenti  
  
1.  Scaricare il progetto dalla soluzione.  
  
     Per altre informazioni sullo scaricamento dei progetti, vedere [NIB: procedura: scaricare e ricaricare i progetti](https://msdn.microsoft.com/library/abc0155b-8fcb-4ffc-95b6-698518a7100b). Se viene chiesto di salvare, scegliere **Sì**.  
  
2.  Aggiungere un nuovo **applicazioni Windows** progetto alla soluzione. Aprire il form nel **progettazione**.  
  
     Il **Componenti ToolboxExample** scheda dal progetto precedente è stata ancora attivo.  
  
3.  Ricarica il `ToolboxExample` progetto.  
  
     Il **Componenti ToolboxExample** scheda ora viene visualizzata di nuovo.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa procedura dettagliata viene dimostrato che la **casella degli strumenti** prende in considerazione i componenti di un progetto, ma la **della casella degli strumenti** è anche dei controlli. Sperimentare con i controlli personalizzati aggiungendo e rimuovendo i progetti di controllo dalla soluzione.  
  
## <a name="see-also"></a>Vedere anche  
 [Generale, finestra di progettazione di Windows Form, finestra di dialogo Opzioni](https://msdn.microsoft.com/library/8dd170af-72f0-4212-b04b-034ceee92834)  
 [Procedura: modificare le schede della Casella degli strumenti](https://msdn.microsoft.com/library/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)](https://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [Inserimento di controlli in Windows Form](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
