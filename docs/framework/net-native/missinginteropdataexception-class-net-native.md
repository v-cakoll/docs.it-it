---
title: Classe MissingInteropDataException (.NET Native)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eab4bcf8-9f5f-4731-87d8-842748a6062a
ms.openlocfilehash: faf14245cd9dd7aa4bf8e89d5a05901279956509
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128275"
---
# <a name="missinginteropdataexception-class-net-native"></a>Classe MissingInteropDataException (.NET Native)
**.NET per app di Windows per Windows 10, solo .NET Native**  
  
 Eccezione generata quando viene chiamato un metodo di marshalling manuale, ma i metadati per un tipo non vengono trovati dall'analisi statica o in un file di direttive di runtime.  
  
 **Spazio dei nomi:** System.Runtime.CompilerServices  
  
> [!IMPORTANT]
> La `MissingInteropDataException` classe è destinata esclusivamente all'uso interno da parte della catena di strumenti .NET native. La classe non può essere usata in codice di terze parti ed è preferibile evitare di gestire l'eccezione nel codice dell'applicazione. Al contrario, eliminare l'eccezione aggiungendo le voci al [file delle direttive di runtime](runtime-directives-rd-xml-configuration-file-reference.md). Per altre informazioni, vedere la sezione Osservazioni.  
  
## <a name="syntax"></a>Sintassi  
 [!code-csharp[ProjectN#21](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missinginteropdataexception_syntax1.cs#21)]
 [!code-vb[ProjectN#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/projectn/vb/missinginteropdataexception_syntax1.vb#21)]  
  
 La classe `MissingInteropDataException` ha i seguenti membri:  
  
## <a name="constructors"></a>Costruttori  
  
|Costruttore|Descrizione|  
|-----------------|-----------------|  
|`public MissingInteropDataException(String resourceId, Type pertinentType)`|Inizializza una nuova istanza della classe `MissingInteropDataException` usando l’ID di un messaggio fornito dal sistema che descrive l'errore e il tipo di cui mancano i dati. Questo costruttore è solo per uso interno da parte della catena di strumenti .NET Native.|  
  
## <a name="properties"></a>Proprietà  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Ottiene una raccolta di coppie chiave/valore che forniscono informazioni definite dall'utente aggiuntive sull'eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public string HelpLink { get; set; }`|Ottiene o imposta un collegamento al file della Guida associato all'eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public int HResult { get; protected set; }`|Ottiene o imposta `HRESULT`, un valore numerico codificato assegnato a una specifica eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public Exception InnerException { get; }`|Ottiene l'eccezione che ha causato l'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public string Message { get; }`|Ottiene un messaggio che descrive l'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public Type MissingType { get; private set; }`|Ottiene o imposta il tipo di cui mancano i dati.|  
|`public string Source { get; set; }`|Ottiene o imposta il nome dell'app o dell'oggetto che ha causato l'errore. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public string StackTrace { get; }`|Ottiene una rappresentazione di stringa dei frame immediati nello stack di chiamate. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public MethodBase TargetSite { get; }`|Ottiene il metodo che ha generato l'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|Determina se l'oggetto specificato è uguale all'oggetto corrente.  Ereditato da <xref:System.Object>.|  
|`protected void Finalize()`|Consente a un oggetto di effettuare un tentativo di liberare risorse ed eseguire altre operazioni di pulizia prima che venga recuperato da Garbage Collection. Ereditato da <xref:System.Object>.|  
|`public Exception GetBaseException()`|Restituisce l'eccezione che rappresenta la causa radice di una o più eccezioni successive. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public int GetHashCode()`|Restituisce un codice hash per un'istanza `MissingInteropDataException`.   Ereditato da <xref:System.Object>.|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Imposta un oggetto <xref:System.Runtime.Serialization.SerializationInfo> con le informazioni relative all'eccezione.  Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public Type GetType()`|Ottiene il tipo di runtime dell'istanza corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`protected Object MemberwiseClone()`|Crea una copia superficiale dell'oggetto corrente. Ereditato da <xref:System.Object>.|  
|`public string ToString()`|Restituisce la rappresentazione di stringa dell'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
  
## <a name="events"></a>Events  
  
|Event|Descrizione|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Si verifica quando un'eccezione viene serializzata per creare un oggetto di stato eccezione contenente i dati serializzati relativi all'eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
  
## <a name="usage-details"></a>Dettagli sull'utilizzo  
 L'eccezione `MissingInteropDataException` viene generata quando una chiamata al metodo a un componente COM o Windows Runtime non riesce perché non sono disponibili le informazioni sul tipo.  
  
 I metadati disponibili per un'app in fase di esecuzione sono definiti dal file di direttive di runtime (configurazione XML), \* . Rd. XML. Per evitare che l'app generi questa eccezione, è necessario modificare il file per definire i metadati che devono essere presenti al runtime. In genere questo errore viene risolto aggiungendo un attributo `MarshalObject`, `MarshalDelegate` o `MarshalStructure` all'elemento di programma appropriato nel file di direttive di runtime. Per informazioni sul formato di questo file, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).  
  
> [!IMPORTANT]
> L'eccezione indica che i metadati richiesti dall'applicazione non sono disponibili in fase di esecuzione. Per questo motivo, l'eccezione non va gestita in un blocco `try`/`catch`. È invece necessario diagnosticare la causa dell'eccezione ed eliminarla usando una voce adatta a un file di direttive di runtime.  
  
 La classe `MissingInteropDataException` contiene un solo membro univoco, la proprietà `MissingType`, che indica il tipo di cui sono richiesti i metadati affinché riesca la chiamata al metodo. Tutti gli altri membri sono ereditati dalla classe base, <xref:System.Exception?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Exception?displayProperty=nameWithType>
- [Classe MissingMetadataException](missingmetadataexception-class-net-native.md)
- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
