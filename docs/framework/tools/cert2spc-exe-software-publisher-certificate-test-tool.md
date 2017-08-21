---
title: Cert2spc.exe (strumento di test dei certificati del distributore di software)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
caps.latest.revision: 21
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7109f96b6997670afa6ef7c362b9e1a142014fbe
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a>Cert2spc.exe (strumento di test dei certificati del distributore di software)
Lo strumento di verifica dei certificati dell'editore del software (Cert2spc.exe) crea un certificato SPC (Software Publisher's Certificate) da uno o più certificati X.509 ed è finalizzato unicamente ai test. È possibile ottenere un certificato SPC valido da un'autorità di certificazione quale VeriSign o Thawte. Per ulteriori informazioni sulla creazione di certificati X.509, vedere [Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) (Makecert.exe, strumento di creazione dei comandi).  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il prompt dei comandi per sviluppatori o il prompt dei comandi di Visual Studio in Windows 7. Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### <a name="parameters"></a>Parametri  
  
|Argomento|Descrizione|  
|--------------|-----------------|  
|`certN.cer`|Il nome di un certificato X.509 da includere nel file SPC. È possibile specificare più nomi separati da spazi.|  
|`crlN.crl`|Il nome di un elenco di revoche di certificati da includere nel file SPC. È possibile specificare più nomi separati da spazi.|  
|`outputSPCfile.spc`|Il nome dell'oggetto PKCS #7 che conterrà i certificati X.509.|  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
## <a name="examples"></a>Esempi  
 Il comando che segue crea un certificato SPC da `myCertificate.cer` e lo inserisce in `mySPCFile.spc`.  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 Il comando che segue crea un certificato SPC da `oneCertificate.cer` e `twoCertificate.cer` e lo inserisce in `mySPCFile.spc`.  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Strumenti](../../../docs/framework/tools/index.md)   
 [Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d)  (Makecert.exe, strumento di creazione certificati)  
 [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

