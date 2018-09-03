---
title: Codificatore ByteStream
ms.date: 03/30/2017
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
ms.openlocfilehash: cbd4110ecc04923b79d6b910fcf7ab4ca2012680
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480692"
---
# <a name="bytestream-encoder"></a>Codificatore ByteStream
In questo esempio descritto come creare una `ByteStreamHttpBinding`, una <xref:System.ServiceModel.Channels.Binding> che dimostra la funzionalità del codificatore del flusso di byte.  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene descritto come creare un oggetto <xref:System.ServiceModel.Channels.Binding> standard usando gli elementi di associazione standard <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> e <xref:System.ServiceModel.Channels.HttpTransportBindingElement>. In questo esempio viene illustrato come usare il codificatore del flusso di byte per caricare e scaricare un'immagine. La funzionalità di codificatore del flusso di byte supporta solo il trasporto HTTP e non supporta funzionalità quali la messaggistica affidabile o la sicurezza. L'unica <xref:System.ServiceModel.Channels.MessageVersion> supportata è <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  
  
> [!IMPORTANT]
>  Se si esegue questo esempio in [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] o [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], verificare di eseguire [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegi elevati.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire il file ByteStreamHttpBinding.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Avviare una nuova istanza del progetto ByteStreamHttpBindingServer facendo clic sul progetto in Esplora soluzioni e selezionando **Debug**e quindi **Avvia nuova istanza** dal menu di scelta rapida.  
  
3.  Avviare una nuova istanza del progetto ByteStreamHttpBindingClient facendo clic sul progetto in Esplora soluzioni e selezionando **Debug**, **Avvia nuova istanza** dal menu di scelta rapida.
