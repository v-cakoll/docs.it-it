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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153777"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<Elemento UseRandomizedStringHashAlgorithm>
Determina se Common Language Runtime calcola i codici hash per le stringhe in base al dominio applicazione.  
  
[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>di runtime**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se i codici hash per le stringhe vengono calcolati in base al dominio applicazione.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|valore|Descrizione|  
|-----------|-----------------|  
|`0`|Common Language Runtime non calcola i codici hash per le stringhe in base al dominio applicazione. un singolo algoritmo viene utilizzato per calcolare i codici hash delle stringhe. Questa è la modalità predefinita.|  
|`1`|Common Language Runtime calcola i codici hash per le stringhe in base al dominio applicazione. Stringhe identiche in domini applicazione diversi e in processi diversi avranno codici hash diversi.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Osservazioni  
 Per impostazione <xref:System.StringComparer> predefinita, <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> la classe e il metodo utilizzano un singolo algoritmo hash che produce un codice hash coerente tra i domini applicazione. Equivale a impostare `enabled` l'attributo dell'elemento `<UseRandomizedStringHashAlgorithm>` su `0`. Si tratta dell'algoritmo hash utilizzato in .NET Framework 4.  
  
 La <xref:System.StringComparer> classe <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> e il metodo possono inoltre utilizzare un algoritmo hash diverso che calcola i codici hash in base al dominio applicazione. Di conseguenza, i codici hash per le stringhe equivalenti saranno diversi tra i domini applicazione. Questa è una funzione di opt-in; per trarne vantaggio, è `enabled` necessario impostare l'attributo dell'elemento `<UseRandomizedStringHashAlgorithm>` su `1`.  
  
 La ricerca di stringhe in una tabella hash è in genere un'operazione O(1). Tuttavia, quando si verifica un numero elevato di conflitti, la ricerca può diventare un'operazione O(n<sup>2</sup>). È possibile `<UseRandomizedStringHashAlgorithm>` utilizzare l'elemento configuration per generare un algoritmo hash casuale per ogni dominio applicazione, che a sua volta limita il numero di potenziali conflitti, in particolare quando le chiavi da cui vengono calcolati i codici hash sono basate sull'immissione di dati da parte degli utenti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato `DisplayString` di seguito viene definita `s`una classe che include una costante di stringa privata, , il cui valore è "This is a string". Viene inoltre incluso un metodo `ShowStringHashCode` tramite cui vengono visualizzati il valore stringa e il codice hash con il nome del dominio applicazione in cui il metodo è in esecuzione.  
  
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
