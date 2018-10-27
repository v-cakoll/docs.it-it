---
title: WCF e nomi IDN (Internationalized Domain Name)
ms.date: 03/30/2017
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
ms.openlocfilehash: a0d4a5b4fe5dd3bc7cf41c8c6ad320dd83861aec
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187923"
---
# <a name="wcf-and-internationalized-domain-names"></a>WCF e nomi IDN (Internationalized Domain Name)
È stato aggiunto il supporto per i servizi WCF con gli IDN (Internationalized Domain Name). Un IDN è un nome di dominio che contiene caratteri non ASCII. Questo supporto include sia la possibilità di ospitare un servizio WCF con un nome IDN sia un client WCF per comunicare con un servizio Web con un nome IDN.  
  
## <a name="systemuri-and-idn"></a>System.Uri e IDN  
 All'oggetto <xref:System.Uri> sono associate due proprietà: <xref:System.Uri.Host%2A> e <xref:System.Uri.DnsSafeHost%2A>. Queste proprietà contengono valori Unicode o Punycode in base alle impostazioni di configurazione IDN.  
  
 IDN viene abilitato nel file di configurazione di un'applicazione usando il seguente codice XML  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
```  
  
 Il \<idn > elemento contiene l'attributo abilitato che può essere impostato su uno dei valori seguenti:  
  
1.  "None"  
  
2.  Utilizzando "AllExceptIntranet"  
  
3.  "Tutti"  
  
 Quando l'impostazione IDN è impostata su "None", viene eseguita alcuna conversione da URI. host o URI. DnsSafeHost. Quando l'impostazione IDN è impostata su "All", uri. Host rimane Unicode e uri. DnsSafeHost viene convertito in Punycode. Quando l'impostazione IDN è impostata su "AllExceptIntranet", uri. DnsSafeHost viene convertito in Punycode per gli indirizzi internet e rimane Unicode per gli indirizzi intranet. Questa impostazione è importante per una corretta risoluzione dei nomi DNS. Si noti che questa impostazione non deve essere configurata per Windows 8 e versioni più recenti.  
  
> [!WARNING]
>  È consigliabile non impostare mai come hardcoded un indirizzo in cui viene usato Punycode. WCF lo convertirà in base alle impostazioni di configurazione che vengano applicate.  
  
> [!WARNING]
>  Quando si aggiungono caratteri Unicode ad applicationHost.exe.config, salvare il file usando la codifica UTF-8.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Uri?displayProperty=nameWithType>
