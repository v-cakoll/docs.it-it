---
title: 'Procedura: Visualizzare i certificati con lo snap-in MMC'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 69f79b64250ff46524e7b4720d13351774875a3f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167505"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Procedura: Visualizzare i certificati con lo snap-in MMC
Quando si crea un client protetto o un servizio, è possibile usare una [certificato](working-with-certificates.md) come le credenziali. Ad esempio, un tipo comune di credenziale è il certificato X.509 che si crea con la <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> (metodo). 

Esistono tre diversi tipi di archivi di certificati che è possibile esaminare con Microsoft Management Console (MMC) nei sistemi Windows:

- Computer locale: L'archivio è locale per il dispositivo e globali per tutti gli utenti del dispositivo.

- Utente corrente: L'archivio è locale all'account utente corrente nel dispositivo.

- Account del servizio: L'archivio è locale rispetto a un determinato servizio nel dispositivo.

## <a name="view-certificates-in-the-mmc-snap-in"></a>Visualizzare i certificati nello snap-in MMC 

La procedura seguente viene illustrato come esaminare gli archivi nel dispositivo locale per trovare un certificato appropriato: 
  
1. Selezionare **eseguiti** dalle **avviare** dal menu e quindi immettere *mmc*. 

    Verrà visualizzata la finestra di MMC. 
  
2. Dal **File** dal menu **Aggiungi/Rimuovi snap-In**. 
    
    Il **Aggiungi o Rimuovi Snap-in** verrà visualizzata la finestra.
  
3. Dal **snap-in disponibili** casella di riepilogo **certificati**, quindi selezionare **Add**.  

    ![Aggiungere lo snap-in certificati](./media/mmc-add-certificate-snap-in.png)
  
4. Nel **snap-in certificati** finestra, seleziona **account Computer**e quindi selezionare **Next**. 
  
    Facoltativamente, è possibile selezionare **account dell'utente** per l'utente corrente oppure **account del servizio** per un determinato servizio. 

    > [!NOTE]
    > Se non si ha un amministratore per il dispositivo, è possibile gestire i certificati solo per l'account utente.
  
5. Nel **seleziona Computer** finestra, lasciare **computer locale** selezionata e quindi selezionare **fine**.  
  
6. Nel **Aggiungi o Rimuovi Snap-in** finestra, seleziona **OK**.  
  
    ![Aggiungere lo snap-in certificati](./media/mmc-certificate-snap-in-selected.png)

7. Facoltative: Dal **File** dal menu **salvare** oppure **Salva con nome** per salvare il file di console MMC per un uso successivo.  

8. Per visualizzare i certificati nello snap-in MMC, selezionare **radice Console** nel riquadro sinistro, quindi espandere **certificati (Computer locale)**.

    Viene visualizzato un elenco di directory per ogni tipo di certificato. Dalla directory ogni certificato, è possibile visualizzare, esportare, importare ed eliminare i propri certificati.

## <a name="view-certificates-with-the-certificate-manager-tool"></a>Visualizzare i certificati con lo strumento di gestione certificati

È anche possibile visualizzare, esportare, importare ed eliminare certificati utilizzando lo strumento di gestione certificati.

### <a name="to-view-certificates-for-the-local-device"></a>Per visualizzare i certificati per il dispositivo locale

1. Selezionare **eseguiti** dalle **avviare** dal menu e quindi immettere *certlm. msc*. 

    Viene visualizzato lo strumento di gestione certificati per il dispositivo locale. 
  
2. Per visualizzare i certificati, in **certificati - Computer locale** nel riquadro sinistro, espandere la directory per il tipo di certificato che si desidera visualizzare.

### <a name="to-view-certificates-for-the-current-user"></a>Per visualizzare i certificati per l'utente corrente

1. Selezionare **eseguiti** dalle **avviare** dal menu e quindi immettere *Certmgr. msc*. 

    Viene visualizzato lo strumento di gestione certificati per l'utente corrente. 
  
2. Per visualizzare i certificati, in **certificati - utente corrente** nel riquadro sinistro, espandere la directory per il tipo di certificato che si desidera visualizzare.

## <a name="see-also"></a>Vedere anche

- [Utilizzo dei certificati](working-with-certificates.md)
- [Procedura: Creare certificati temporanei da usare durante lo sviluppo](how-to-create-temporary-certificates-for-use-during-development.md)
- [Procedura: Recuperare l'identificazione personale di un certificato](how-to-retrieve-the-thumbprint-of-a-certificate.md)
