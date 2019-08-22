---
title: Elemento <idn> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 5fe2eafee702be96bfdca80a06af4a040d9ef0f6
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664129"
---
# <a name="idn-element-uri-settings"></a>\<Elemento > IDN (impostazioni URI)
Specifica se l'analisi del nome di dominio internazionale (IDN) viene applicata a un nome di dominio.  
  
## <a name="schema-hierarchy"></a>Gerarchia dello schema  
 [Elemento \<configuration>](../configuration-element.md)  
  
 [\<Elemento > URI (impostazioni URI)](uri-element-uri-settings.md)  
  
 [\<idn>](idn-element-uri-settings.md)  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<idn  
  enabled="All|AllExceptIntranet|None"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|`enabled`|Specifica se l'analisi del nome di dominio internazionale (IDN) viene applicata a un nome di dominio. il valore predefinito è None.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).|  
  
## <a name="remarks"></a>Note  
 La classe <xref:System.Uri> esistente è stata estesa in .NET Framework 3,5. 3,0 SP1 e 2,0 SP1 con supporto per gli identificatori di risorse internazionali (IRI) e i nomi di dominio internazionali (IDN). Gli utenti correnti non vedranno alcuna modifica rispetto al comportamento di .NET Framework 2,0, a meno che non vengano specificamente abilitati il supporto di IRI e IDN. Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.  
  
 Per abilitare il supporto per IRI, sono necessarie le due modifiche seguenti:  
  
1. Aggiungere la riga seguente al file Machine. config nella directory .NET Framework 2,0  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. Specificare se si desidera che l'analisi del nome di dominio internazionalizzazione (IDN) venga applicata al nome di dominio e se devono essere applicate le regole di analisi IRI. A questo scopo, è possibile usare il file machine.config o il file app.config.  
  
 Esistono tre possibili valori per IDN a seconda dei server DNS utilizzati:  
  
- IDN abilitato = tutti  
  
     Questo valore convertirà i nomi di dominio Unicode negli equivalenti Punycode (nomi IDN).  
  
- IDN abilitato = AllExceptIntranet  
  
     Questo valore convertirà tutti i nomi di dominio Unicode non presenti nella rete Intranet locale per utilizzare gli equivalenti Punycode (nomi IDN). In questo caso, per gestire i nomi internazionali sulla Intranet locale, i server DNS utilizzati per la Intranet devono supportare la risoluzione dei nomi Unicode.  
  
- IDN abilitato = None  
  
     Con questo valore non verrà convertito alcun nome di dominio Unicode per l'utilizzo di Punycode. Si tratta del valore predefinito, coerente con il comportamento .NET Framework 2,0.  
  
 L'abilitazione degli IDN comporta la conversione di tutte le etichette Unicode in un nome di dominio nei rispettivi equivalenti Punycode. I nomi Punycode contengono solo caratteri ASCII e iniziano sempre con il prefisso "xn--". Questo avviene per supportare i server DNS esistenti in Internet, in quanto la maggior parte dei server DNS supporta solo caratteri ASCII. Vedere il documento RFC 3940.  
  
### <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>DESCRIZIONE  
 Nell'esempio seguente viene illustrata una configurazione utilizzata <xref:System.Uri> dalla classe per supportare l'analisi IRI e i nomi IDN.  
  
### <a name="code"></a>Codice  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
