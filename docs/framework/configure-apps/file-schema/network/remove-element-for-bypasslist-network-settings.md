---
title: Elemento <remove> per bypasslist (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove element, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: 0fd8de9af00aa861d92c8c201ef89545e108c790
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659231"
---
# <a name="remove-element-for-bypasslist-network-settings"></a>\<Rimuovi elemento > per l'elemento bypass (impostazioni di rete)

Rimuove un indirizzo IP o un nome DNS dall'elenco di bypass del proxy.

\<> di configurazione \
\<System. net > \
\<defaultProxy>\
\<> di bypass \
\<remove>

## <a name="syntax"></a>Sintassi

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a>Attributi ed elementi

Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.

### <a name="attributes"></a>Attributi

|**Attributo**|**Descrizione**|
|-------------------|---------------------|
|`address`|Espressione regolare che descrive un indirizzo IP o un nome DNS.|

### <a name="child-elements"></a>Elementi figlio

Nessuno.

### <a name="parent-elements"></a>Elementi padre

|**Elemento**|**Descrizione**|
|-----------------|---------------------|
|[bypasslist](bypasslist-element-network-settings.md)|Fornisce un set di espressioni regolari che descrivono gli indirizzi che non utilizzano un proxy.|

## <a name="remarks"></a>Note

L' `remove` elemento rimuove le espressioni regolari che descrivono gli indirizzi IP o i nomi dei server DNS dall'elenco di indirizzi che ignorano un server proxy. Gli indirizzi sono stati definiti in precedenza nel file di configurazione o a un livello superiore nella gerarchia di configurazione.

Il valore `address` dell'attributo deve essere un'espressione regolare che descrive un set di indirizzi IP o nomi host.

Per ulteriori informazioni sulle espressioni regolari, vedere. [.NET Framework espressioni regolari](../../../../../docs/standard/base-types/regular-expressions.md).

## <a name="configuration-files"></a>File di configurazione

Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).

## <a name="example"></a>Esempio

Nell'esempio seguente viene rimossa qualsiasi definizione precedente per il dominio adventure-works.com, quindi viene aggiunto il dominio contoso.com all'elenco di bypass.

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <bypasslist>
        <remove address="[a-z]+\.adventure-works\.com$" />
        <add address="[a-z]+\.contoso\.com$" />
      </bypasslist>
    </defaultProxy>
  </system.net>
</configuration>
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
