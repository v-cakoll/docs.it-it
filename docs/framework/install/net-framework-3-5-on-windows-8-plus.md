---
title: Installare .NET Framework 3.5 in Windows 8, Windows 8.1 e Windows 10
ms.date: 05/26/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
helpviewer_keywords:
- .NET Framework 3.5, installing on Windows 8
- Windows 8, installing .NET Framework 3.5
ms.assetid: 3eab3eb4-4573-42ac-98f8-36fb2c22c7d5
caps.latest.revision: 69
author: mairaw
ms.author: mairaw
ms.translationtype: HT
ms.sourcegitcommit: 20b0c1b36f705deb2f46ef4ab23653f829faf7ca
ms.openlocfilehash: 8a0395e28c01363eed27f327ea623feb4832c844
ms.contentlocale: it-it
ms.lasthandoff: 08/08/2017

---

# <a name="install-the-net-framework-35-on-windows-8-windows-81-and-windows-10"></a>Installare .NET Framework 3.5 in Windows 8, Windows 8.1 e Windows 10

.NET Framework è parte integrante di molte app in esecuzione su Windows e offre funzionalità comuni per l'esecuzione di tali app. Per gli sviluppatori, .NET Framework offre un modello di programmazione coerente per lo sviluppo di applicazioni. Se si usa il sistema operativo Windows, .NET Framework potrebbe essere già installato nel computer. In particolare, [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] è incluso con [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] è incluso con [!INCLUDE[win81](../../../includes/win81-md.md)] e [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] è incluso con Windows 10.  
  
.NET Framework 3.5 non viene tuttavia installato automaticamente con [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] o Windows 10 e deve essere abilitato separatamente per eseguire le app che dipendono da questa versione. Ciò deve verificarsi tramite Windows Update, che viene richiamato in uno dei tre modi seguenti. Per tutte le opzioni è necessaria una connessione Internet.  
  
- [Installare .NET Framework 3.5 su richiesta](#OnDemand)  
  
- [Abilitare .NET Framework 3.5 dal Pannello di controllo](#ControlPanel)  
  
- [Scaricare il programma di installazione di .NET Framework 3.5](http://www.microsoft.com/en-us/download/details.aspx?id=21) Nota: non viene scaricato direttamente .NET Framework, ma un programma di installazione che chiama Windows Update.  
  
Durante l'installazione può verificarsi un errore 0x800f0906, 0x800f0907 o 0x800f081f. In tal caso, vedere [Errore di installazione di .NET Framework 3.5: 0x800f0906, 0x800f0907, 0x800f081f](https://support.microsoft.com/en-us/kb/2734782). Si noti che questo problema può essere risolto installando l' [aggiornamento della sicurezza 3005628](https://support.microsoft.com/kb/3005628).  
  
Se uno dei metodi sopra riportati non riesce o non è presente una connessione Internet, è necessario usare il supporto di installazione di Windows. Per altre informazioni, vedere Metodo 3 per l'errore 0x800f0906 nell'articolo [Errore di installazione .NET Framework 3.5](https://support.microsoft.com/en-us/kb/2734782). Se il supporto di installazione non è disponibile, vedere [Creare un supporto di installazione per Windows 8.1](http://windows.microsoft.com/en-US/windows-8/create-reset-refresh-media?woldogcb=0).  
  
**Note importanti:**
  
- In genere le versioni di .NET Framework installate nel computer non devono essere disinstallate. App diverse dipendono da versioni diverse del framework e nello stesso computer possono coesistere più versioni di .NET Framework contemporaneamente.  
  
- .NET Framework 3.5 viene usato anche per le app compilate per le versioni 2.0 e 3.0.  
  
- Se si installa un Language Pack Windows prima di .NET Framework 3.5, l'installazione di .NET Framework 3.5 potrebbe non riuscire. Installare .NET Framework 3.5 prima di installare i Language Pack Windows.  
  
- Windows CardSpace non è disponibile con .NET Framework 3.5 in [!INCLUDE[win8](../../../includes/win8-md.md)].  
  
- A causa di problemi relativi alla procedura di installazione di .NET Framework 3.5, non è disponibile un programma di installazione separato e autonomo eseguibile indipendentemente da Windows Update. Se tutti gli altri metodi hanno esito negativo, è necessario ricorrere al supporto di installazione come descritto in precedenza.  
  
<a name="OnDemand"></a>   
## <a name="install-the-net-framework-35-on-demand"></a>Installare .NET Framework 3.5 su richiesta

Se un'app richiede .NET Framework 3.5 ma la versione non è abilitata nel computer in uso, quando si installa l'applicazione o la si esegue per la prima volta viene visualizzata la seguente finestra di messaggio. Nella finestra di messaggio scegliere **Installa la funzionalità** per abilitare .NET Framework 3.5. Per questa opzione è necessaria una connessione Internet.  
  
![Finestra di dialogo per l'installazione della versione 3.5 in Windows 8](../../../docs/framework/deployment/media/installdialog.png "installdialog")  
  
<a name="ControlPanel"></a>   
## <a name="enable-the-net-framework-35-in-control-panel"></a>Abilitare .NET Framework 3.5 dal Pannello di controllo

.NET Framework 3.5 può essere abilitato dal Pannello di controllo. Per questa opzione è necessaria una connessione Internet.  
  
1. Premere il tasto Windows ![Logo Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") sulla tastiera. Digitare "Funzionalità Windows" e premere INVIO. Verrà visualizzata la finestra di dialogo **Attivazione o disattivazione delle funzionalità Windows** . In alternativa, aprire Pannello di controllo, fare clic sugli elementi **Programmi** e quindi fare clic su **Attivazione o disattivazione delle funzionalità Windows** in **Programmi e funzionalità**.  
  
2. Selezionare la casella di controllo **.NET Framework 3.5 (include .NET 2.0 e 3.0)**, selezionare **OK** e riavviare il computer, se richiesto.  
  
Non è necessario selezionare gli elementi figlio per l'**attivazione HTTP di Windows Communication Foundation (WCF)** a meno che, come sviluppatore, non si richieda la funzionalità di mapping del gestore e degli script WCF.
  
## <a name="see-also"></a>Vedere anche

[Guida all'installazione](../../../docs/framework/get-started/index.md)

