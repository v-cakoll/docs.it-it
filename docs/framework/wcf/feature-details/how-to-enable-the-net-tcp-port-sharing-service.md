---
title: 'Procedura: attivare il servizio di condivisione delle porte Net.TCP'
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 4b5a18e11d9fc15f23b5353883a63d838face58a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490760"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Procedura: attivare il servizio di condivisione delle porte Net.TCP
Windows Communication Foundation (WCF) usa un servizio Windows denominato il servizio di condivisione porte Net. TCP per facilitare la condivisione delle porte TCP tra più processi. Questo servizio viene installato come parte di WCF, ma il servizio non è abilitato per impostazione predefinita come misura di sicurezza e pertanto è necessario abilitare manualmente prima di primo utilizzo. In questo argomento viene illustrato come configurare il servizio di condivisione delle porte Net TCP usando lo snap-in MMC (Microsoft Management Console).  
  
 Dopo aver abilitato il servizio di condivisione porta Net. TCP e avviarlo manualmente, vedere [procedura: configurare un servizio WCF di utilizzare la condivisione delle porte](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) per informazioni su come configurare il servizio per l'utilizzo di questo servizio.  
  
 Per un esempio che utilizza la condivisione delle porte net.tcp://, vedere il [esempio di condivisione porta Net. TCP](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>Per attivare il servizio di condivisione delle porte Net.TCP tramite MMC  
  
1.  Dal menu Start, aprire la Console di gestione dei servizi aprendo una finestra del prompt dei comandi e digitando `services.msc` o aprendo Esegui e digitando `services.msc` nella casella Apri.  
  
2.  Nel **nome** colonna dell'elenco di servizi, fare doppio clic su di **servizio di condivisione porte Net. TCP**e selezionare **proprietà** dal menu.  
  
3.  Per abilitare l'avvio manuale del servizio, nel **proprietà** finestra selezionare il **generale** scheda e il **tipo di avvio** casella selezionare manuale e quindi fare clic su **Applicare**.  
  
4.  Per avviare il servizio, nell'area di stato del servizio, fare clic su di **avviare** pulsante. Lo stato del servizio dovrebbe ora essere "Avviato".  
  
5.  Per tornare all'elenco dei servizi, fare clic su di **OK**e uscire dalla Console di MMC.  
  
## <a name="example"></a>Esempio  
  
## <a name="see-also"></a>Vedere anche  
 [Condivisione delle porte Net.TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [Configurazione del servizio di condivisione delle porte Net.TCP](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
