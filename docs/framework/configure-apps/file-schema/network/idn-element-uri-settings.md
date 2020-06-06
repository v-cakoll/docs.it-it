---
title: Elemento <idn> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 16c8e869-1791-4cf5-9244-3d3c738f60ec
ms.openlocfilehash: 533b2562f6e5c8d6c2bf452e56dff9a8bf8ab376
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "71698169"
---
# <a name="idn-element-uri-settings"></a>Elemento \<idn> (impostazioni URI)

Specifica se l'analisi del nome di dominio internazionale (IDN) viene applicata a un nome di dominio.
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<idn>**  
  
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

nessuno
  
### <a name="parent-elements"></a>Elementi padre

|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[URI](uri-element-uri-settings.md)|Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).|  

## <a name="remarks"></a>Commenti

La <xref:System.Uri> classe esistente è stata estesa in .NET Framework 3,5. 3,0 SP1 e 2,0 SP1 con supporto per gli identificatori di risorse internazionali (IRI) e i nomi di dominio internazionali (IDN). Gli utenti correnti non vedranno alcuna modifica rispetto al comportamento di .NET Framework 2,0, a meno che non vengano specificamente abilitati il supporto di IRI e IDN. Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.

Per abilitare il supporto per IRI, sono necessarie le due modifiche seguenti:

1. Aggiungere la riga seguente al file Machine. config nella directory .NET Framework 2,0:
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. Specificare se si desidera che l'analisi del nome di dominio internazionalizzazione (IDN) venga applicata al nome di dominio e se devono essere applicate le regole di analisi IRI. A questo scopo, è possibile usare il file machine.config o il file app.config.

 Esistono tre possibili valori per IDN a seconda dei server DNS utilizzati:

- IDN abilitato = tutti  

     Questo valore convertirà qualsiasi nome di dominio Unicode negli equivalenti Punycode (nomi IDN).

- IDN abilitato = AllExceptIntranet

     Questo valore convertirà tutti i nomi di dominio Unicode non presenti nella rete Intranet locale per utilizzare gli equivalenti Punycode (nomi IDN). In questo caso, per gestire i nomi internazionali sulla Intranet locale, i server DNS utilizzati per la Intranet devono supportare la risoluzione dei nomi Unicode.

- IDN abilitato = None

     Questo valore non convertirà alcun nome di dominio Unicode per l'utilizzo di Punycode Si tratta del valore predefinito coerente con il comportamento di .NET Framework 2.0.

 L'abilitazione degli IDN comporta la conversione di tutte le etichette Unicode in un nome di dominio nei rispettivi equivalenti Punycode. I nomi Punycode contengono solo caratteri ASCII e iniziano sempre con il prefisso "xn--". Questo avviene per supportare i server DNS esistenti in Internet, in quanto la maggior parte dei server DNS supporta solo caratteri ASCII. Vedere il documento RFC 3940.

### <a name="configuration-files"></a>File di configurazione

Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata una configurazione utilizzata dalla <xref:System.Uri> classe per supportare l'analisi IRI e i nomi IDN:

```xml
<configuration>
  <uri>
    <idn enabled="All" />
    <iriParsing enabled="true" />
  </uri>
</configuration>
```

## <a name="see-also"></a>Vedi anche

- <xref:System.Configuration.IdnElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
