---
title: 'Procedura: Avviare servizi'
description: Scopri diversi modi per avviare i servizi. Dopo l'installazione di un servizio, è necessario avviarlo. L'avvio chiama il metodo OnStart sulla classe del servizio.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
ms.openlocfilehash: 4a2f9b291e60b12b1465fbb6bbbd1604572359a7
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925722"
---
# <a name="how-to-start-services"></a>Procedura: Avviare servizi

Dopo l'installazione di un servizio, è necessario avviarlo. Con l'avvio viene chiamato il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> per la classe del servizio. In genere, il metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> definisce le operazioni utili che verranno eseguite dal servizio. Dopo l'avvio, un servizio rimane attivo fino a quando non viene sospeso o arrestato manualmente.

I servizi possono essere configurati per l'avvio automatico o manuale. Un servizio con avvio automatico verrà avviato in seguito al riavvio o alla prima accensione del computer in cui è installato. Un utente deve avviare un servizio con avvio manuale.

> [!NOTE]
> Per impostazione predefinita, i servizi creati con Visual Studio vengono impostati per l'avvio manuale.

Esistono diversi modi per avviare manualmente un servizio, ovvero da **Esplora server**, da **Gestione controllo servizi** o dal codice usando un componente denominato <xref:System.ServiceProcess.ServiceController>.

Per determinare se un servizio deve essere avviato manualmente o automaticamente, è possibile impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> per la classe <xref:System.ServiceProcess.ServiceInstaller>.

### <a name="to-specify-how-a-service-should-start"></a>Per specificare come avviare un servizio

1. Dopo aver creato il servizio, aggiungere i programmi di installazione necessari. Per altre informazioni, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).

2. Nella finestra di progettazione fare clic sul programma di installazione per il servizio in uso.

3. Nella finestra **Proprietà** impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> su uno dei valori seguenti:

    |Per installare il servizio|Impostare questo valore|
    |----------------------------------|--------------------|
    |Al riavvio del computer|**Automatico**|
    |Quando un'azione esplicita dell'utente avvia il servizio|**Manuale**|

    > [!TIP]
    > Per impedire del tutto l'avvio del servizio, è possibile impostare la proprietà <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> su **Disabled**. Ciò può essere utile se si prevede di dover riavviare un server più volte e si vuole risparmiare tempo evitando l'avvio dei servizi che verrebbero normalmente avviati.

    > [!NOTE]
    > Queste e altre proprietà possono essere modificate dopo l'installazione del servizio.

    Esistono diversi modi per avviare un servizio con il processo <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> impostato su **Manual**, ovvero da **Esplora server**, da **Gestione controllo servizi** o dal codice. È importante notare che non tutti questi metodi avviano effettivamente il servizio nel contesto di **Gestione controllo servizi**. **Esplora server** e i metodi a livello di codice di avvio del servizio modificano effettivamente il controller.

### <a name="to-manually-start-a-service-from-server-explorer"></a>Per avviare manualmente un servizio da Esplora server

1. In **Esplora server** aggiungere il server desiderato, se non è già elencato. Per altre informazioni, vedere Procedura: Accedere e inizializzare Esplora server-Esplora database.

2. Espandere il nodo **Servizi** e quindi individuare il servizio che si vuole avviare.

3. Fare clic con il pulsante destro del mouse sul nome del servizio e quindi scegliere **Avvia**.

### <a name="to-manually-start-a-service-from-services-control-manager"></a>Per avviare manualmente un servizio da Gestione controllo servizi

1. Aprire **Gestione controllo servizi** eseguendo una delle operazioni seguenti:

    - In Windows XP e 2000 Professional fare clic con il pulsante destro del mouse su **Risorse del computer** e quindi scegliere **Gestisci**. Nella finestra di dialogo visualizzata espandere il nodo **Servizi e applicazioni**.

      \- - oppure -

    - In Windows Server 2003 e Windows 2000 Server fare clic su **Start**, scegliere **Programmi**, fare clic su **Strumenti di amministrazione** e quindi fare clic su **Servizi**.

      > [!NOTE]
      > In Windows NT versione 4.0 è possibile aprire questa finestra di dialogo dal **Pannello di controllo**.

    Il servizio dovrebbe essere a questo punto elencato nella sezione **Servizi** della finestra.

2. Fare clic con il pulsante destro del mouse sul servizio dopo averlo selezionato nell'elenco e quindi scegliere **Avvia**.

### <a name="to-manually-start-a-service-from-code"></a>Per avviare manualmente un servizio da codice

1. Creare un'istanza della classe <xref:System.ServiceProcess.ServiceController> e configurarla per interagire con il servizio che si vuole amministrare.

2. Chiamare il metodo <xref:System.ServiceProcess.ServiceController.Start%2A> per avviare il servizio.

## <a name="see-also"></a>Vedere anche

- [Introduzione alle applicazioni di servizio Windows](introduction-to-windows-service-applications.md)
- [Procedura: Creare servizi Windows](how-to-create-windows-services.md)
- [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md)
