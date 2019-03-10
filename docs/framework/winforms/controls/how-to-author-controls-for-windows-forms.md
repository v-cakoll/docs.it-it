---
title: 'Procedura: Creare controlli per Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
ms.openlocfilehash: 38416f28546f2aebc04d9ecf2c6995282b4720b8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713413"
---
# <a name="how-to-author-controls-for-windows-forms"></a>Procedura: Creare controlli per Windows Form
Un controllo rappresenta un collegamento grafico tra l'utente e il programma. Un controllo può fornire o elaborare dati, accettare input dall'utente, rispondere a eventi o eseguire qualsiasi numero di altre funzioni che connettono l'utente e l'applicazione. Poiché un controllo è essenzialmente un componente con un'interfaccia grafica, può essere utilizzato per le stesse funzioni di un componente oltre che per consentire l'interazione dell'utente. I controlli vengono creati per scopi specifici e la creazione di controlli è semplicemente un'altra attività di programmazione. Tenendo conto di questo, i passaggi seguenti rappresentano una panoramica del processo di creazione di un controllo. I collegamenti forniscono altre informazioni sui singoli passaggi.  
  
> [!NOTE]
>  Per creare un controllo personalizzato da usare nei Web Form, vedere [Sviluppo di controlli server ASP.NET personalizzati](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).  
>   
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-author-a-control"></a>Per creare un controllo  
  
1.  Determinare ciò il controllo dovrà fare o quale ruolo svolgerà nell'applicazione. I fattori da considerare sono:  
  
    -   Quale tipo di interfaccia grafica è necessario?  
  
    -   Quali specifiche interazioni dell'utente saranno gestite da questo controllo?  
  
    -   Le funzionalità necessarie sono fornite da ogni controllo esistente?  
  
    -   È possibile ottenere le funzionalità richieste combinando diversi controlli Windows Form?  
  
2.  Se è necessario un modello di oggetti per il controllo, stabilire come le funzionalità verranno distribuite nel modello di oggetti e suddividere le funzionalità tra il controllo e gli eventuali oggetti secondari. Un modello di oggetti può essere utile se si intende creare un controllo complesso o si desidera incorporare varie funzionalità.  
  
3.  Determinare il tipo di controllo necessario (ad esempio controllo utente, controllo personalizzato, controllo Windows Form ereditato). Per informazioni dettagliate, vedere [Consigli sui tipi di controlli](control-type-recommendations.md) e [Tipi di controlli personalizzati](varieties-of-custom-controls.md).  
  
4.  Definire le funzionalità come proprietà, metodi ed eventi del controllo e i relativi oggetti secondari o strutture secondarie e assegnare i livelli di accesso appropriati (ad esempio pubblico, protetto e così via).  
  
5.  Se è necessario un disegno personalizzato per il controllo, aggiungere codice per esso. Per informazioni dettagliate, vedere [Disegno e rendering di controlli personalizzati](custom-control-painting-and-rendering.md).  
  
6.  Se il controllo eredita da <xref:System.Windows.Forms.UserControl>, è possibile verificarne il comportamento di runtime compilando il progetto di controllo ed eseguendolo nel **UserControl Test Container**. Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
7.  È possibile testare ed eseguire il debug del controllo anche creando un nuovo progetto, ad esempio un'applicazione Windows, e inserendolo in un contenitore. Questo processo viene illustrato come parte di [procedura dettagliata: Modifica di un controllo composito con Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md).  
  
8.  Quando si aggiunge ogni funzionalità, aggiungere le funzionalità al progetto di test per verificarne il funzionamento.  
  
9. Ripetere l'operazione, ottimizzando la struttura.  
  
10. Creare il pacchetto e distribuire il controllo. Per informazioni dettagliate, vedere [primi passi in fase di distribuzione in Visual Studio](/visualstudio/deployment/deploying-applications-services-and-components).  
  
## <a name="see-also"></a>Vedere anche
- [Procedura dettagliata: Modifica di un controllo composito con Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [Procedura dettagliata: Eredità da un controllo di Windows Forms con Visual Basic](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [Procedura: Ereditare dalla classe UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Procedura: Ereditare dalla classe Control](how-to-inherit-from-the-control-class.md)
- [Procedura: Ereditare da esistenti di Windows Form](how-to-inherit-from-existing-windows-forms-controls.md)
- [Procedura: Testare il comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
