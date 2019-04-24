---
title: Cert2spc.exe (strumento di test dei certificati del distributore di software)
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 079c48a9975861646f1d28338d02dab8e4775031
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101237"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a>Cert2spc.exe (strumento di test dei certificati del distributore di software)
Lo strumento di verifica dei certificati dell'editore del software (Cert2spc.exe) crea un certificato SPC (Software Publisher's Certificate) da uno o più certificati X.509 ed è finalizzato unicamente ai test. È possibile ottenere un certificato SPC valido da un'autorità di certificazione quale VeriSign o Thawte. Per ulteriori informazioni sulla creazione di certificati X.509, vedere [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert) (Makecert.exe, strumento di creazione dei comandi).  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
## <a name="parameters"></a>Parametri  
  
|Argomento|Description|  
|--------------|-----------------|  
|`certN.cer`|Il nome di un certificato X.509 da includere nel file SPC. È possibile specificare più nomi separati da spazi.|  
|`crlN.crl`|Il nome di un elenco di revoche di certificati da includere nel file SPC. È possibile specificare più nomi separati da spazi.|  
|`outputSPCfile.spc`|Il nome dell'oggetto PKCS #7 che conterrà i certificati X.509.|  
  
|Opzione|Description|  
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

- [Strumenti](../../../docs/framework/tools/index.md)
- [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert) (Makecert.exe, strumento di creazione certificati)
- [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
