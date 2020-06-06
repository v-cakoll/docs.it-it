---
title: <UseRandomizedStringHashAlgorithm> Elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153777"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<UseRandomizedStringHashAlgorithm> Elemento
Determina se il Common Language Runtime calcola i codici hash per le stringhe in base al dominio dell'applicazione.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se i codici hash per le stringhe vengono calcolati in base al dominio dell'applicazione.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Description|  
|-----------|-----------------|  
|`0`|Il Common Language Runtime non calcola i codici hash per le stringhe in base al dominio dell'applicazione. viene utilizzato un singolo algoritmo per calcolare i codici hash della stringa. Questo è il valore predefinito.|  
|`1`|Il Common Language Runtime calcola i codici hash per le stringhe in base al dominio dell'applicazione. Stringhe identiche in domini applicazione diversi e in processi diversi avranno codici hash diversi.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Commenti  
 Per impostazione predefinita, la <xref:System.StringComparer> classe e il <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> Metodo usano un unico algoritmo di hashing che produce un codice hash coerente tra i domini applicazione. Equivale a impostare l' `enabled` attributo dell' `<UseRandomizedStringHashAlgorithm>` elemento su `0` . Si tratta dell'algoritmo hash utilizzato nel .NET Framework 4.  
  
 La <xref:System.StringComparer> classe e il <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> metodo possono anche usare un algoritmo di hash diverso che calcola i codici hash in base al dominio dell'applicazione. Di conseguenza, i codici hash per le stringhe equivalenti si differenziano tra domini applicazione. Si tratta di una funzionalità di consenso esplicito; per sfruttarlo, è necessario impostare l' `enabled` attributo dell' `<UseRandomizedStringHashAlgorithm>` elemento su `1` .  
  
 La ricerca di stringhe in una tabella hash è in genere un'operazione O (1). Tuttavia, quando si verifica un numero elevato di conflitti, la ricerca può diventare un'operazione O (n<sup>2</sup>). È possibile usare l' `<UseRandomizedStringHashAlgorithm>` elemento di configurazione per generare un algoritmo di hashing casuale per ogni dominio dell'applicazione, che a sua volta limita il numero di potenziali collisioni, in particolare quando le chiavi da cui vengono calcolati i codici hash sono basate sull'input dei dati da parte degli utenti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definita una `DisplayString` classe che include una costante di stringa privata, `s` , il cui valore è "This is a String". Viene inoltre incluso un metodo `ShowStringHashCode` tramite cui vengono visualizzati il valore stringa e il codice hash con il nome del dominio applicazione in cui il metodo è in esecuzione.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 Quando si esegue l'esempio senza fornire un file di configurazione, restituisce un output analogo al seguente. Si noti che i codici hash per la stringa sono identici nei due domini applicazione.  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Tuttavia, se si aggiunge il file di configurazione seguente alla directory di esempio e, successivamente, si esegue l'esempio, i codici hash per la stessa stringa risulteranno diversi dal dominio dell'applicazione.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 Quando il file di configurazione è presente, l'esempio visualizza il seguente output:  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
