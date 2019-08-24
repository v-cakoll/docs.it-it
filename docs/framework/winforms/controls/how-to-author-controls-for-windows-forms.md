---
title: 'Procedura: Creare controlli per Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 45a6ae68102204ad8506027065c2676e02fdd7a3
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015923"
---
# <a name="how-to-author-controls-for-windows-forms"></a>Procedura: Controlli autore per Windows Forms

Un controllo rappresenta un collegamento grafico tra l'utente e il programma. Un controllo può fornire o elaborare dati, accettare input dall'utente, rispondere a eventi o eseguire qualsiasi numero di altre funzioni che connettono l'utente e l'applicazione. Poiché un controllo è essenzialmente un componente con un'interfaccia grafica, può essere utilizzato per le stesse funzioni di un componente oltre che per consentire l'interazione dell'utente. I controlli vengono creati per scopi specifici e la creazione di controlli è semplicemente un'altra attività di programmazione. Tenendo conto di questo, i passaggi seguenti rappresentano una panoramica del processo di creazione di un controllo. I collegamenti forniscono altre informazioni sui singoli passaggi.

## <a name="to-author-a-control"></a>Per creare un controllo

1. Determinare ciò il controllo dovrà fare o quale ruolo svolgerà nell'applicazione. I fattori da considerare sono:

    - Quale tipo di interfaccia grafica è necessario?

    - Quali specifiche interazioni dell'utente saranno gestite da questo controllo?

    - Le funzionalità necessarie sono fornite da ogni controllo esistente?

    - È possibile ottenere le funzionalità richieste combinando diversi controlli Windows Form?

2. Se è necessario un modello di oggetti per il controllo, stabilire come le funzionalità verranno distribuite nel modello di oggetti e suddividere le funzionalità tra il controllo e gli eventuali oggetti secondari. Un modello di oggetti può essere utile se si intende creare un controllo complesso o si desidera incorporare varie funzionalità.

3. Determinare il tipo di controllo necessario (ad esempio controllo utente, controllo personalizzato, controllo Windows Form ereditato). Per informazioni dettagliate, vedere [Consigli sui tipi di controlli](control-type-recommendations.md) e [Tipi di controlli personalizzati](varieties-of-custom-controls.md).

4. Definire le funzionalità come proprietà, metodi ed eventi del controllo e i relativi oggetti secondari o strutture secondarie e assegnare i livelli di accesso appropriati (ad esempio pubblico, protetto e così via).

5. Se è necessario un disegno personalizzato per il controllo, aggiungere codice per esso. Per informazioni dettagliate, vedere [Disegno e rendering di controlli personalizzati](custom-control-painting-and-rendering.md).

6. Se il controllo eredita da <xref:System.Windows.Forms.UserControl>, è possibile verificarne il comportamento in fase di esecuzione compilando il progetto di controllo ed eseguendolo nel **contenitore di test UserControl**. Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)UserControl.

7. È possibile testare ed eseguire il debug del controllo anche creando un nuovo progetto, ad esempio un'applicazione Windows, e inserendolo in un contenitore. Questo processo viene illustrato come parte della [procedura dettagliata: Creazione di un controllo](walkthrough-authoring-a-composite-control-with-visual-csharp.md)composito.

8. Quando si aggiunge ogni funzionalità, aggiungere le funzionalità al progetto di test per verificarne il funzionamento.

9. Ripetere l'operazione, ottimizzando la struttura.

10. Creare il pacchetto e distribuire il controllo. Per informazioni dettagliate, vedere la pagina relativa [alla prima occhiata alla distribuzione in Visual Studio](/visualstudio/deployment/deploying-applications-services-and-components).

## <a name="see-also"></a>Vedere anche

- [Procedura: Ereditare dalla classe UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Procedura: Ereditare dalla classe Control](how-to-inherit-from-the-control-class.md)
- [Procedura: Ereditare da controlli Windows Forms esistenti](how-to-inherit-from-existing-windows-forms-controls.md)
- [Procedura: Testare il comportamento in fase di esecuzione di un UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
