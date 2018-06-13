---
title: '&lt;UseRandomizedStringHashAlgorithm&gt; elemento'
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
ms.openlocfilehash: a515c3011905c4f5c18ed9d3e8edf489428c04d8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746085"
---
# <a name="ltuserandomizedstringhashalgorithmgt-element"></a>&lt;UseRandomizedStringHashAlgorithm&gt; elemento
Determina se common language runtime calcola il codice hash per le stringhe in una base di un dominio di applicazione.  
  
 \<configuration>  
\<runtime>  
\<UseRandomizedStringHashAlgorithm >  
  
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
|`enabled`|Attributo obbligatorio.<br /><br /> Specifica se i codici hash per le stringhe vengono calcolati in una base di un dominio di applicazione.|  
  
## <a name="enabled-attribute"></a>Attributo enabled  
  
|Valore|Descrizione|  
|-----------|-----------------|  
|`0`|Common language runtime non calcolare i codici hash per le stringhe in una per ogni singolo dominio di applicazione; un solo algoritmo viene utilizzato per calcolare i codici hash di stringa. Questa è l'impostazione predefinita.|  
|`1`|Common language runtime consente di calcolare i codici hash per le stringhe in una base di un dominio di applicazione. Stringhe identiche in diversi domini applicazione e in diversi processi avranno i codici hash diverso.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|`configuration`|Elemento radice in ciascun file di configurazione usato in Common Language Runtime e nelle applicazioni .NET Framework.|  
|`runtime`|Contiene informazioni sulle opzioni di inizializzazione in fase di esecuzione.|  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, il <xref:System.StringComparer> classe e <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> metodo utilizza un solo algoritmo hash che genera un codice hash coerente tra domini dell'applicazione. Questo è equivalente all'impostazione di `enabled` attributo del `<UseRandomizedStringHashAlgorithm>` elemento `0`. Si tratta dell'algoritmo hash utilizzato nel [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 Il <xref:System.StringComparer> classe e <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> metodo può anche usare un algoritmo di hash diverso che consente di calcolare i codici hash in una base di un dominio di applicazione. Di conseguenza, i codici hash per le stringhe equivalente variano tra domini dell'applicazione. È una funzionalità che prevede il consenso esplicito; Per sfruttare i vantaggi di esso, è necessario impostare il `enabled` attributo del `<UseRandomizedStringHashAlgorithm>` elemento `1`.  
  
 La ricerca della stringa in una tabella hash è in genere un'operazione o (1). Tuttavia, quando si verifica un numero elevato di conflitti, la ricerca può diventare un'operazione O (n<sup>2</sup>) operazione. È possibile utilizzare il `<UseRandomizedStringHashAlgorithm>` elemento di configurazione per generare un algoritmo di hash caso per ogni dominio applicazione, che a sua volta limita il numero di potenziali conflitti, in particolare quando le chiavi da cui vengono calcolati i codici hash sono basate su dati di input da parte degli utenti.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce un `DisplayString` classe che include una costante di stringa privata, `s`, il cui valore è "This is a una stringa". Include inoltre un `ShowStringHashCode` metodo che visualizza il valore di stringa e il codice hash insieme al nome del dominio dell'applicazione in cui l'esecuzione del metodo.  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 Quando si esegue l'esempio senza fornire un file di configurazione, viene visualizzato l'output simile al seguente. Si noti che i codici hash per la stringa siano identici in due domini applicazione.  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 Tuttavia, se si aggiunge il file di configurazione seguente alla directory dell'esempio e quindi eseguire l'esempio, i codici hash per la stessa stringa diverso dal dominio applicazione.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 Quando il file di configurazione è presente, nell'esempio viene visualizzato il seguente output:  
  
```  
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>  
 <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
