---
title: 'Procedura dettagliata: esecuzione di attività comuni utilizzando gli smart tag nei controlli Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: a558f6d274f260fc91fd140e9dae2c740b1ae00d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537944"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>Procedura dettagliata: esecuzione di attività comuni utilizzando gli smart tag nei controlli Windows Form
Come si creano i form e controlli per l'applicazione Windows Form, sono disponibili numerose attività che verranno eseguite più volte. Queste sono alcune delle attività comunemente svolte che si verificheranno:  
  
-   Aggiunta o rimozione di una scheda in un <xref:System.Windows.Forms.TabControl>.  
  
-   Ancoraggio di un controllo al relativo elemento padre.  
  
-   Modifica dell'orientamento di un <xref:System.Windows.Forms.SplitContainer> controllo.  
  
 Per velocizzare lo sviluppo, molti controlli offrono gli smart tag sono menu sensibile al contesto che consentono di eseguire attività comuni come in un singolo movimento in fase di progettazione. Queste attività vengono chiamate *verbi di smart tag*.  
  
 Gli smart tag rimanere connessi a un'istanza di controllo per la relativa durata nella finestra di progettazione e sono sempre disponibili.  
  
 Le attività illustrate nella procedura dettagliata sono le seguenti:  
  
-   Creazione di un progetto Windows Form  
  
-   Utilizzando gli smart tag  
  
-   Abilitazione e disabilitazione Smart tag  
  
 Al termine, si avrà una migliore comprensione del ruolo svolto da queste importanti funzionalità di layout.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="creating-the-project"></a>Creazione del progetto  
 Il primo passaggio consiste nella creazione del progetto e nella configurazione del form.  
  
#### <a name="to-create-the-project"></a>Per creare il progetto  
  
1.  Creare un progetto di applicazione basata su Windows denominato "SmartTagsExample". Per informazioni dettagliate, vedere [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Selezionare il form nel **Progettazione Windows Form**.  
  
## <a name="using-smart-tags"></a>Utilizzando gli Smart tag  
 Gli smart tag sono sempre disponibili in fase di progettazione per controlli quali sono disponibili.  
  
#### <a name="to-use-smart-tags"></a>Utilizzo di smart tag  
  
1.  Trascinare un <xref:System.Windows.Forms.TabControl> dal **della casella degli strumenti** nel form. Si noti il glifo smart tag (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) che viene visualizzato sul lato del <xref:System.Windows.Forms.TabControl>.  
  
2.  Fare clic sull'icona di smart tag. Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare il **Aggiungi scheda** elemento. Si osservi che una nuova pagina della scheda viene aggiunta per il <xref:System.Windows.Forms.TabControl>.  
  
3.  Trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo il **della casella degli strumenti** nel form.  
  
4.  Fare clic sull'icona di smart tag. Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare il **Aggiungi colonna** elemento. Osservare che viene aggiunta una nuova colonna per il <xref:System.Windows.Forms.TableLayoutPanel> controllo.  
  
5.  Trascinare un <xref:System.Windows.Forms.SplitContainer> controllo il **della casella degli strumenti** nel form.  
  
6.  Fare clic sull'icona di smart tag. Nel menu di scelta rapida che viene visualizzato accanto all'icona, selezionare il **orientamento separatore orizzontale** elemento. Osservare che il <xref:System.Windows.Forms.SplitContainer> barra di divisione del controllo è orientato in orizzontale.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [Procedura dettagliata: Aggiunta di Smart tag per un componente di Windows Form](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
