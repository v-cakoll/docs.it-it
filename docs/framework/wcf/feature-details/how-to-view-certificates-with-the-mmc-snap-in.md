---
title: 'Procedura: visualizzare certificati con lo snap-in MMC'
description: Un client o un servizio WCF sicuro può utilizzare un certificato come credenziale. Informazioni sui tipi di archivi certificati che è possibile esaminare tramite il plug-in MMC.
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: e63034e48ae836f67f89b454829f7196c94610cd
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246675"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a>Procedura: visualizzare certificati con lo snap-in MMC
Quando si crea un client o un servizio protetto, è possibile usare un [certificato](working-with-certificates.md) come credenziale. Ad esempio, un tipo comune di credenziale è il certificato X. 509, creato con il <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> metodo.

Sono disponibili tre diversi tipi di archivi certificati che è possibile esaminare con Microsoft Management Console (MMC) nei sistemi Windows:

- Computer locale: l'archivio è locale per il dispositivo e globale per tutti gli utenti del dispositivo.

- Utente corrente: l'archivio è locale per l'account utente corrente nel dispositivo.

- Account del servizio: l'archivio è locale per un servizio specifico nel dispositivo.

## <a name="view-certificates-in-the-mmc-snap-in"></a>Visualizzare i certificati nello snap-in MMC

La procedura seguente illustra come esaminare gli archivi sul dispositivo locale per trovare un certificato appropriato:
  
1. Selezionare **Esegui** dal menu **Start** , quindi immettere *MMC*.

    Viene visualizzata la console MMC.
  
2. Scegliere **Aggiungi/Rimuovi snap-in**dal menu **file** .

    Verrà visualizzata la finestra **Aggiungi o Rimuovi snap-** in.
  
3. Dall'elenco **snap-in disponibili** scegliere **certificati**, quindi selezionare **Aggiungi**.  

    ![Aggiungi snap-in certificati](./media/mmc-add-certificate-snap-in.png)
  
4. Nella finestra **snap-in certificati** selezionare **account computer**e quindi fare clic su **Avanti**.
  
    Facoltativamente, è possibile selezionare l' **account utente** per l'account utente o del **servizio** corrente per un servizio specifico.

    > [!NOTE]
    > Se non si è un amministratore del dispositivo, è possibile gestire i certificati solo per l'account utente.
  
5. Nella finestra **Seleziona computer** lasciare selezionata l'opzione **computer locale** e quindi fare clic su **fine**.  
  
6. Nella finestra **Aggiungi o Rimuovi snap-in** fare clic su **OK**.  
  
    ![Aggiungi snap-in certificati](./media/mmc-certificate-snap-in-selected.png)

7. Facoltativo: dal menu **file** selezionare **Salva** o Salva con **nome** per salvare il file della console MMC per un uso successivo.  

8. Per visualizzare i certificati nello snap-in MMC, selezionare **radice console** nel riquadro sinistro, quindi espandere **certificati (computer locale)**.

    Viene visualizzato un elenco di directory per ogni tipo di certificato. Da ogni directory dei certificati è possibile visualizzare, esportare, importare ed eliminare i relativi certificati.

## <a name="view-certificates-with-the-certificate-manager-tool"></a>Visualizzare i certificati con lo strumento Gestione certificati

È inoltre possibile visualizzare, esportare, importare ed eliminare certificati utilizzando lo strumento Gestione certificati.

### <a name="to-view-certificates-for-the-local-device"></a>Per visualizzare i certificati per il dispositivo locale

1. Selezionare **Esegui** dal menu **Start** , quindi immettere *certlm. msc*.

    Viene visualizzato lo strumento Gestione certificati per il dispositivo locale.
  
2. Per visualizzare i certificati, in **certificati-computer locale** nel riquadro sinistro, espandere la directory per il tipo di certificato che si desidera visualizzare.

### <a name="to-view-certificates-for-the-current-user"></a>Per visualizzare i certificati per l'utente corrente

1. Selezionare **Esegui** dal menu **Start** , quindi immettere *certmgr. msc*.

    Viene visualizzato lo strumento Gestione certificati per l'utente corrente.
  
2. Per visualizzare i certificati, in **certificati-utente corrente** nel riquadro sinistro, espandere la directory per il tipo di certificato che si desidera visualizzare.

## <a name="see-also"></a>Vedere anche

- [Utilizzo dei certificati](working-with-certificates.md)
- [Procedura: creare certificati temporanei da usare durante lo sviluppo](how-to-create-temporary-certificates-for-use-during-development.md)
- [Procedura: recuperare l'identificazione personale di un certificato](how-to-retrieve-the-thumbprint-of-a-certificate.md)
