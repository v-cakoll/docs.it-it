---
title: 'Procedura: Abilitare il servizio di condivisione delle porte Net.TCP'
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 77d1d983da87b37c6267cc38a16db446782797f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130650"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Procedura: Abilitare il servizio di condivisione delle porte Net.TCP
Windows Communication Foundation (WCF) usano un servizio Windows denominato il servizio di condivisione porte Net. TCP per semplificare la condivisione delle porte TCP tra più processi. Questo servizio viene installato come parte di WCF, ma il servizio non è abilitato per impostazione predefinita come misura di sicurezza e pertanto è necessario abilitare manualmente prima del primo utilizzo. In questo argomento viene illustrato come configurare il servizio di condivisione delle porte Net TCP usando lo snap-in MMC (Microsoft Management Console).  
  
 Dopo aver abilitato il servizio di condivisione porte Net. TCP e avviarlo manualmente, vedere [come: Configurare un servizio WCF di utilizzare la condivisione delle porte](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) per informazioni su come configurare il servizio per usare questo servizio.  
  
 Per un esempio che usa net.tcp:// condivisione delle porte, vedere la [esempio di condivisione porta Net. TCP](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>Per attivare il servizio di condivisione delle porte Net.TCP tramite MMC  
  
1.  Dal menu Start, aprire la Console di Gestione servizi aprendo una finestra del prompt dei comandi e digitando `services.msc` o aprendo Esegui e digitando `services.msc` nella casella Apri.  
  
2.  Nel **Name** colonna dell'elenco dei servizi, fare doppio clic sui **servizio di condivisione porte Net. TCP**e selezionare **proprietà** dal menu di scelta.  
  
3.  Per abilitare l'avvio manuale del servizio, nel **proprietà** finestra selezionare il **generali** della scheda e nella **tipo di avvio** finestra selezionare manuale e quindi fare clic su **Applicare**.  
  
4.  Per avviare il servizio, nell'area dello stato del servizio, scegliere il **avviare** pulsante. Lo stato del servizio dovrebbe ora essere "Avviato".  
  
5.  Per tornare all'elenco dei servizi, scegliere il **OK**e chiudere la Console MMC.  
  
## <a name="example"></a>Esempio  
  
## <a name="see-also"></a>Vedere anche

- [Condivisione delle porte Net.TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [Configurazione del servizio di condivisione delle porte Net.TCP](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
