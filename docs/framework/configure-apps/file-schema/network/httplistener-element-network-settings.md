---
title: '&lt;httpListener&gt; elemento (impostazioni di rete)'
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a327f757f26c815d5b2cffe179af68bbe3d152eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="lthttplistenergt-element-network-settings"></a>&lt;httpListener&gt; elemento (impostazioni di rete)
Consente di personalizzare i parametri utilizzati per la <xref:System.Net.HttpListener> classe.  
  
 \<configuration>  
\<system.net>  
\<Impostazioni >  
\<httpListener >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a>Tipo  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|unescapeRequestUrl|Un valore booleano che indica se un <xref:System.Net.HttpListener> istanza utilizza l'URI senza caratteri escape non elaborato anziché l'URI convertito.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[Impostazioni](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Note  
 Il **unescapeRequestUrl** attributo indica se <xref:System.Net.HttpListener> utilizza l'URI senza caratteri escape non elaborato anziché l'URI convertito in cui vengono convertiti i valori codificati in percentuale e vengono eseguiti altri passaggi di normalizzazione.  
  
 Quando un <xref:System.Net.HttpListener> istanza riceve una richiesta tramite il `http.sys` servizio, crea un'istanza della stringa URI fornita da `http.sys`e lo espone come il <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> proprietà.  
  
 Il `http.sys` servizio espone due stringhe URI di richiesta:  
  
-   URI non elaborato  
  
-   URI convertito  
  
 L'URI non elaborato il <xref:System.Uri?displayProperty=nameWithType> fornito nella riga della richiesta di una richiesta HTTP:  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 L'URI non elaborato fornito da `http.sys` per è indicata in precedenza, la richiesta di "percorso /". Rappresenta la stringa che segue il verbo HTTP, come è stato inviato in rete.  
  
 Il `http.sys` servizio crea un URI convertito dalle informazioni fornite nella richiesta utilizzando l'URI specificato nella riga della richiesta HTTP e l'intestazione Host per determinare il server di origine la richiesta deve essere inoltrato a. Questa operazione viene eseguita confrontando le informazioni della richiesta con un set di prefissi URI registrati. La documentazione SDK Server HTTP fa riferimento all'URI convertito come la struttura HTTP_COOKED_URL.  
  
 Per poter essere in grado di confrontare la richiesta con i prefissi URI registrati, deve essere eseguita la normalizzazione della richiesta. Nell'esempio precedente l'URI convertito sarà come segue:  
  
 `http://www.contoso.com/path/`  
  
 Il `http.sys` servizio combina il <xref:System.Uri.Host%2A?displayProperty=nameWithType> valore della proprietà e la stringa nella riga della richiesta per creare un URI convertito. Inoltre, `http.sys` e <xref:System.Uri?displayProperty=nameWithType> classe esegue inoltre le operazioni seguenti:  
  
-   Non consente l'escape tutte le percentuali di valori codificati.  
  
-   Caratteri non ASCII converte codificati in percentuale in una rappresentazione dei caratteri UTF-16. Si noti che i caratteri UTF-8 e ANSI o DBCS sono supportati anche i caratteri Unicode (codifica Unicode utilizzando il formato % uXXXX).  
  
-   Consente di eseguire altri passaggi di normalizzazione, come la compressione del percorso.  
  
 Poiché la richiesta non contiene alcuna informazione sulla codifica utilizzata per i valori codificati in percentuale, potrebbe non essere possibile determinare la codifica corretta solo analizzando i valori codificati in percentuale.  
  
 Pertanto `http.sys` fornisce due chiavi del Registro di sistema per la modifica del processo:  
  
|Chiave del Registro di sistema|Valore predefinito|Descrizione|  
|------------------|-------------------|-----------------|  
|EnableNonUTF8|1|Se è zero, `http.sys` accetta solo URL con codifica UTF-8.<br /><br /> Se diverso da zero, `http.sys` accetta anche URL con codifica ANSI o DBCS nelle richieste.|  
|FavorUTF8|1|Se diverso da zero, `http.sys` sempre eseguito un tentativo di decodificare un URL come UTF-8 per primo; se tale conversione non riesce ed EnableNonUTF8 è diverso da zero, Http.sys quindi tenta di decodificarlo come ANSI o DBCS.<br /><br /> Se è zero (ed EnableNonUTF8 è diverso da zero), `http.sys` eseguito un tentativo di decodificare come ANSI o DBCS; se non è riuscita, prova una conversione di UTF-8.|  
  
 Quando <xref:System.Net.HttpListener> riceve una richiesta, viene utilizzato l'URI convertito da `http.sys` come input per il <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.  
  
 È necessario supportare i caratteri oltre ai caratteri e numeri negli URI. Un esempio è il seguente URI utilizzato per recuperare informazioni sul cliente per il cliente numero "1/3812":  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 Si noti la barra codificati in percentuale nell'Uri (% 2F). Questa operazione è necessaria, poiché in questo caso il carattere di barra rappresenta dati e non un delimitatore di percorso.  
  
 Passare la stringa al costruttore Uri determinerà l'URI seguente:  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 Il percorso di suddivisione in segmenti comporta i seguenti elementi:  
  
 `Customer('1`  
  
 `3812')`  
  
 Non è lo scopo del mittente della richiesta.  
  
 Se il **unescapeRequestUrl** attributo è impostato su **false**, successivamente, quando il <xref:System.Net.HttpListener> riceve una richiesta, viene utilizzato l'URI non elaborato anziché l'URI convertito da `http.sys` come input per il <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.  
  
 Il valore predefinito per il **unescapeRequestUrl** attributo **true**.  
  
 Il <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> utilizzabile per ottenere il valore corrente della proprietà di **unescapeRequestUrl** attributo dal file di configurazione applicabili.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come configurare il <xref:System.Net.HttpListener> classe quando riceve una richiesta di usare l'URI non elaborato anziché l'URI convertito da `http.sys` come input per il <xref:System.Net.HttpListenerRequest.Url%2A> proprietà.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a>Informazioni sull'elemento  
  
|||
|-|-|  
|Spazio dei nomi|System.Net|  
|Nome di schema||  
|File di convalida||  
|Può essere vuoto||  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.Configuration.HttpListenerElement>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpListenerRequest.Url%2A>  
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
