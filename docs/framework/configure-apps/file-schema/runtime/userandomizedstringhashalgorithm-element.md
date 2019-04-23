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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a51b9fb485da605effbad0e81b8baf5e05e382a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087794"
---
# <a name="userandomizedstringhashalgorithm-element"></a>\<UseRandomizedStringHashAlgorithm > elemento
Determina se common language runtime calcola i codici hash per le stringhe in una base di dominio dell'applicazione.  
  
 \<configuration>  
\<runtime>  
\<UseRandomizedStringHashAlgorithm>  
  
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
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se i codici hash per le stringhe vengono calcolati su una base di dominio dell'applicazione.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`0`|Common language runtime non calcola i codici hash per le stringhe in una base al dominio applicazione; un singolo algoritmo viene utilizzato per calcolare i codici hash di stringa. Questa è l'impostazione predefinita.|  
|`1`|Common language runtime calcola i codici hash per le stringhe in una base di dominio dell'applicazione. Stringhe identiche in domini applicazione diversi e in processi diversi avranno i codici hash differenti.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, il <xref:System.StringComparer> classe e il <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> metodo usare un singolo algoritmo di hash che produce un codice hash coerente tra più domini applicazione. Ciò equivale a impostare il `enabled` attributo del `<UseRandomizedStringHashAlgorithm>` elemento `0`. Questo è l'algoritmo hash usato nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 Il <xref:System.StringComparer> classe e il <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> metodo può anche usare un algoritmo di hash diverso che calcola i codici hash in una base di dominio dell'applicazione. Di conseguenza, i codici hash per le stringhe equivalenti risulteranno diversi tra i domini dell'applicazione. Si tratta di una funzionalità che prevede il consenso esplicito; Per sfruttare i vantaggi di esso, è necessario impostare il `enabled` attributo del `<UseRandomizedStringHashAlgorithm>` elemento `1`.  
  
 La ricerca di stringhe in una tabella hash è in genere un'operazione o (1). Tuttavia, quando si verificano numerosi conflitti, la ricerca può diventare un'operazione O (n<sup>2</sup>) operazione. È possibile usare il `<UseRandomizedStringHashAlgorithm>` elemento di configurazione per generare un algoritmo di hash casuale per ogni dominio applicazione, che a sua volta limita il numero di potenziali conflitti, in particolare quando le chiavi da cui i codici hash vengono calcolati sono basate su immissione dei dati dagli utenti.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce una `DisplayString` classe che include una costante di stringa privata, `s`, il cui valore è "This is a una stringa". Include inoltre un `ShowStringHashCode` metodo che consente di visualizzare il valore della stringa e il codice hash con il nome del dominio dell'applicazione in cui l'esecuzione del metodo.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 Quando si esegue l'esempio senza fornire un file di configurazione, viene visualizzato output simile al seguente. Si noti che i codici hash per la stringa sono identici in due domini applicazione.  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Tuttavia, se si aggiunge il file di configurazione seguente alla directory di esempio e quindi eseguire l'esempio, i codici hash per la stessa stringa risulteranno diversi dal dominio dell'applicazione.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 Quando il file di configurazione è presente, l'esempio visualizza l'output seguente:  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
