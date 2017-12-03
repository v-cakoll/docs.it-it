---
title: 'Procedura: visualizzare certificati con lo snap-in MMC'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5981e68ebe2870870fff5e92e87d7582ac2c42b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Procedura: visualizzare certificati con lo snap-in MMC
Un tipo comune di credenziale è il certificato X.509. Al momento di creare servizi o client protetti, è possibile specificare il certificato che deve essere utilizzato come credenziale client o del servizio tramite metodi come, ad esempio, <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>. Il metodo richiede vari parametri, ad esempio l'archivio in cui il certificato è memorizzato e un valore da utilizzare quando si cerca il certificato. Nella procedura seguente viene illustrato come esaminare gli archivi in un computer per trovare un certificato adatto. Per un esempio di ricerca di identificazione personale del certificato, vedere [procedura: recuperare l'identificazione personale del certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a>Per visualizzare certificati nello snap-in MMC  
  
1.  Aprire una finestra del prompt dei comandi.  
  
2.  Tipo `mmc` e premere INVIO. Si noti che per visualizzare certificati nell'archivio del computer locale, è necessario avere il ruolo di Amministratore.  
  
3.  Nel **File** menu, fare clic su **Aggiungi/Rimuovi snap-In**.  
  
4.  Fare clic su **Aggiungi**.  
  
5.  Nel **Aggiungi Snap-in Standalone** nella finestra di dialogo **certificati**.  
  
6.  Fare clic su **Aggiungi**.  
  
7.  Nel **snap-in certificati** nella finestra di dialogo **account Computer** e fare clic su **Avanti**. Facoltativamente, è possibile selezionare **account dell'utente** o **account del servizio**. Se non si è un amministratore del computer, è possibile gestire i certificati solo per il proprio account utente.  
  
8.  Nel **seleziona Computer** la finestra di dialogo, fare clic su **fine**.  
  
9. Nel **Aggiungi Snap-in Standalone** la finestra di dialogo, fare clic su **Chiudi**.  
  
10. Nel **Aggiungi/Rimuovi Snap-in** la finestra di dialogo, fare clic su **OK**.  
  
11. Nel **radice Console** finestra, fare clic su **certificati (Computer locale)** per visualizzare i certificati vengono archiviati per il computer.  
  
12. Parametro facoltativo. Per visualizzare i certificati per il proprio account, ripetere i passaggi da 3 a 6. Nel passaggio 7, anziché selezionare **account Computer**, fare clic su **account dell'utente** e ripetere i passaggi da 8 a 10.  
  
13. Parametro facoltativo. Nel **File** menu, fare clic su **salvare** o **Salva con nome**. Salvare il file di console per riutilizzarlo in seguito.  
  
## <a name="viewing-certificates-with-internet-explorer"></a>Visualizzazione di certificati con Internet Explorer  
 È anche possibile visualizzare, esportare, importare ed eliminare certificati utilizzando Internet Explorer.  
  
#### <a name="to-view-certificates-with-internet-explorer"></a>Per visualizzare certificati con Internet Explorer  
  
1.  In Internet Explorer, fare clic su **strumenti**, quindi fare clic su **Opzioni Internet** per visualizzare il **Opzioni Internet** la finestra di dialogo.  
  
2.  Fare clic su di **contenuto** scheda.  
  
3.  In **certificati**, fare clic su **certificati**.  
  
4.  Per visualizzare i dettagli di un certificato, selezionare il certificato e fare clic su **vista**.  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Procedura: creare certificati temporanei da usare durante lo sviluppo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)  
 [Procedura: recuperare l'identificazione personale del certificato](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
