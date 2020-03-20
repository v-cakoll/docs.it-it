---
title: 'Procedura: visualizzare i certificati con lo snap-in MMC'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184775"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Procedura: visualizzare i certificati con lo snap-in MMC
Quando si crea un client o un servizio sicuro, è possibile usare un [certificato](working-with-certificates.md) come credenziale. Ad esempio, un tipo comune di credenziale è il <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> certificato X.509, creato con il metodo .

Esistono tre diversi tipi di archivi certificati che è possibile esaminare con Microsoft Management Console (MMC) nei sistemi Windows:

- Computer locale: l'archivio è locale per il dispositivo e globale per tutti gli utenti del dispositivo.

- Utente corrente: l'archivio è locale all'account utente corrente nel dispositivo.

- Account del servizio: l'archivio è locale per un determinato servizio nel dispositivo.

## <a name="view-certificates-in-the-mmc-snap-in"></a>Visualizzare i certificati nello snap-in MMC

Nella procedura seguente viene illustrato come esaminare gli archivi nel dispositivo locale per trovare un certificato appropriato:
  
1. Selezionare **Esegui** dal menu **Start,** quindi immettere *mmc*.

    Viene visualizzata la console MMC.
  
2. Dal menu **File,** selezionare **Aggiungi/Rimuovi snap-in**.

    Viene visualizzata la finestra **Aggiungi o rimuovi snap-in.**
  
3. Nell'elenco **Snap-in disponibili** scegliere **Certificati**, quindi **selezionare Aggiungi**.  

    ![Aggiungi snap-in certificati](./media/mmc-add-certificate-snap-in.png)
  
4. Nella finestra **dello snap-in Certificati** selezionare **Account computer**, quindi scegliere **Avanti**.
  
    Facoltativamente, è possibile selezionare **Account utente** personale per l'utente corrente o Account **del servizio** per un determinato servizio.

    > [!NOTE]
    > Se non sei un amministratore del tuo dispositivo, puoi gestire i certificati solo per il tuo account utente.
  
5. Nella finestra **Seleziona computer** lasciare selezionata l'opzione **Computer locale** e quindi selezionare **Fine**.  
  
6. Nella finestra **Aggiungi o rimuovi snap-in** selezionare **OK**.  
  
    ![Aggiungi snap-in certificati](./media/mmc-certificate-snap-in-selected.png)

7. Facoltativo: dal menu **File,** selezionare **Salva** o **Salva con nome** per salvare il file della console MMC per un utilizzo successivo.  

8. Per visualizzare i certificati nello snap-in MMC, selezionare **Radice console** nel riquadro sinistro, quindi espandere **Certificati (computer locale)**.

    Viene visualizzato un elenco di directory per ogni tipo di certificato. Da ogni directory dei certificati è possibile visualizzarne, esportarne, importarne ed eliminarli.

## <a name="view-certificates-with-the-certificate-manager-tool"></a>Visualizzare i certificati con lo strumento Gestione certificati

È inoltre possibile visualizzare, esportare, importare ed eliminare certificati utilizzando lo strumento Gestione certificati.

### <a name="to-view-certificates-for-the-local-device"></a>Per visualizzare i certificati per il dispositivo locale

1. Selezionare **Esegui** dal menu **Start** , quindi immettere *certlm.msc*.

    Viene visualizzato lo strumento Gestione certificati per il dispositivo locale.
  
2. Per visualizzare i certificati, in **Certificati - Computer locale** nel riquadro sinistro espandere la directory per il tipo di certificato che si desidera visualizzare.

### <a name="to-view-certificates-for-the-current-user"></a>Per visualizzare i certificati per l'utente corrente

1. Selezionare **Esegui** dal menu **Start** , quindi immettere *certmgr.msc*.

    Viene visualizzato lo strumento Gestione certificati per l'utente corrente.
  
2. Per visualizzare i certificati, in **Certificati - Utente corrente** nel riquadro sinistro espandere la directory per il tipo di certificato che si desidera visualizzare.

## <a name="see-also"></a>Vedere anche

- [Utilizzo dei certificati](working-with-certificates.md)
- [Procedura: Creare certificati temporanei da utilizzare durante lo sviluppoHow to: Create temporary certificates for use during development](how-to-create-temporary-certificates-for-use-during-development.md)
- [Procedura: recuperare l'identificazione personale di un certificatoHow to: Retrieve the thumbprint of a certificate](how-to-retrieve-the-thumbprint-of-a-certificate.md)
