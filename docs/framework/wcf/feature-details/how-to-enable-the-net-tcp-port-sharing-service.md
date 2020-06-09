---
title: 'Procedura: attivare il servizio di condivisione delle porte Net.TCP'
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 8b305b98d620636328866bce848411f395053485
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593133"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Procedura: attivare il servizio di condivisione delle porte Net.TCP
Windows Communication Foundation (WCF) utilizza un servizio Windows denominato servizio di condivisione porte net. TCP per facilitare la condivisione delle porte TCP tra più processi. Questo servizio viene installato come parte di WCF, ma il servizio non è abilitato per impostazione predefinita come misura di sicurezza e pertanto deve essere abilitato manualmente prima del primo utilizzo. In questo argomento viene illustrato come configurare il servizio di condivisione delle porte Net TCP usando lo snap-in MMC (Microsoft Management Console).  
  
 Dopo aver abilitato il servizio di condivisione porte net. TCP e averlo avviato manualmente, vedere [procedura: configurare un servizio WCF per l'uso della condivisione delle porte](how-to-configure-a-wcf-service-to-use-port-sharing.md) per informazioni su come configurare il servizio per l'uso di questo servizio.  
  
 Per un esempio che usa la condivisione delle porte net. TCP://, vedere l' [esempio di condivisione delle porte net. TCP](../samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>Per attivare il servizio di condivisione delle porte Net.TCP tramite MMC  
  
1. Dal menu Start aprire la console di gestione dei servizi aprendo una finestra del prompt dei comandi e digitando `services.msc` o aprendo Esegui e digitando `services.msc` nella casella Apri.  
  
2. Nella colonna **nome** dell'elenco dei servizi fare clic con il pulsante destro del mouse sul **servizio di condivisione porte net. TCP**e scegliere **proprietà** dal menu.  
  
3. Per abilitare l'avvio manuale del servizio, nella finestra **Proprietà** selezionare la scheda **generale** e nella casella **tipo di avvio** selezionare manuale, quindi fare clic su **applica**.  
  
4. Per avviare il servizio, nell'area stato servizio fare clic sul pulsante **Avvia** . Lo stato del servizio dovrebbe ora essere "Avviato".  
  
5. Per tornare all'elenco dei servizi, fare clic su **OK**e chiudere la console MMC.  
  
## <a name="example"></a>Esempio  
  
## <a name="see-also"></a>Vedere anche

- [Condivisione delle porte Net.TCP](net-tcp-port-sharing.md)
- [Configurazione del servizio di condivisione delle porte Net.TCP](configuring-the-net-tcp-port-sharing-service.md)
