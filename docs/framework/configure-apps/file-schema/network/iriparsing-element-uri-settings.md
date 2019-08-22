---
title: Elemento <iriParsing> (impostazioni URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 2c99edf2f1a03e0e510858c106cad43b0eaa27b4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664080"
---
# <a name="iriparsing-element-uri-settings"></a>\<Elemento > iriParsing (impostazioni URI)
Specifica se l'analisi IRI (International Resource Identifier) viene applicata a un <xref:System.Uri> e se devono essere applicate le regole di analisi IRI.  
  
## <a name="schema-hierarchy"></a>Gerarchia dello schema  
 [Elemento \<configuration>](../configuration-element.md)  
  
 [\<Elemento > URI (impostazioni URI)](uri-element-uri-settings.md)  
  
 [\<iriParsing>](iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|`enabled`|Specifica se è abilitata l'analisi IRI. Il valore predefinito è `false`.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[uri](uri-element-uri-settings.md)|Contiene le impostazioni che specificano il modo in cui il .NET Framework gestisce gli indirizzi Web espressi tramite URI (Uniform Resource Identifier).|  
  
## <a name="remarks"></a>Note  
 La classe <xref:System.Uri> esistente è stata estesa in .NET Framework 3,5. 3,0 SP1 e 2,0 SP1 per fornire supporto per gli identificatori di risorse internazionali (IRI) e i nomi di dominio internazionali (IDN). Gli utenti correnti non vedranno alcuna modifica rispetto al comportamento di .NET Framework 2,0, a meno che non vengano specificamente abilitati il supporto di IRI e IDN. Questo garantisce la compatibilità delle applicazioni con le versioni precedenti di .NET Framework.  
  
 Per abilitare il supporto per IRI, sono necessarie le due modifiche seguenti:  
  
1. Aggiungere la riga seguente al file Machine. config nella directory .NET Framework 2,0  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. Consente di specificare se devono essere applicate le regole di analisi IRI. A questo scopo, è possibile usare il file machine.config o il file app.config.  
  
 L'abilitazione dell'analisi IRI (iriParsing `true`Enabled =) consente di eseguire la normalizzazione e il controllo dei caratteri in base alle regole IRI più recenti nella specifica RFC 3987. Il valore predefinito è `false` e effettuerà la normalizzazione e il controllo dei caratteri in base a RFC 2396 e RFC 3986 (per i valori letterali IPv6).  
  
### <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
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

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
