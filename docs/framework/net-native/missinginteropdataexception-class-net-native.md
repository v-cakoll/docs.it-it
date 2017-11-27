---
title: Classe MissingInteropDataException (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: eab4bcf8-9f5f-4731-87d8-842748a6062a
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0a7e1c02b6404f9511032d18f260726d1493d202
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="missinginteropdataexception-class-net-native"></a>Classe MissingInteropDataException (.NET Native)
**.NET per app di Windows per Windows 10, solo per [!INCLUDE[net_native](../../../includes/net-native-md.md)]**  
  
 Eccezione generata quando viene chiamato un metodo di marshalling manuale, ma i metadati per un tipo non vengono trovati dall'analisi statica o in un file di direttive di runtime.  
  
 **Spazio dei nomi:** System.Runtime.CompilerServices  
  
> [!IMPORTANT]
>  La classe `MissingInteropDataException` è destinata esclusivamente all'uso interno da parte della catena di strumenti [!INCLUDE[net_native](../../../includes/net-native-md.md)]. La classe non può essere usata in codice di terze parti ed è preferibile evitare di gestire l'eccezione nel codice dell'applicazione. Al contrario, eliminare l'eccezione aggiungendo le voci al [file delle direttive di runtime](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Per altre informazioni, vedere la sezione Osservazioni.  
  
## <a name="syntax"></a>Sintassi  
 [!code-csharp[ProjectN#21](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missinginteropdataexception_syntax1.cs#21)]
 [!code-vb[ProjectN#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/projectn/vb/missinginteropdataexception_syntax1.vb#21)]  
  
 La classe `MissingInteropDataException` ha i seguenti membri:  
  
## <a name="constructors"></a>Costruttori  
  
|Costruttore|Descrizione|  
|-----------------|-----------------|  
|`public MissingInteropDataException(String resourceId, Type pertinentType)`|Inizializza una nuova istanza della classe `MissingInteropDataException` usando l’ID di un messaggio fornito dal sistema che descrive l'errore e il tipo di cui mancano i dati. Questo costruttore è destinato a un uso interno da parte della sola catena di strumenti del [!INCLUDE[net_native](../../../includes/net-native-md.md)].|  
  
## <a name="properties"></a>Proprietà  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Ottiene una raccolta di coppie chiave-valore che fornisce informazioni aggiuntive definite dall'utente relative all'eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
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
|`public Exception GetBaseException()`|Restituisce l'eccezione che rappresenta la causa principale di una o più eccezioni successive. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public int GetHashCode()`|Restituisce un codice hash per un'istanza `MissingInteropDataException`.   Ereditato da <xref:System.Object>.|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Imposta un oggetto <xref:System.Runtime.Serialization.SerializationInfo> con le informazioni relative all'eccezione.  Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public Type GetType()`|Ottiene il tipo di runtime dell'istanza corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`protected Object MemberwiseClone()`|Crea una copia superficiale dell'oggetto corrente. Ereditato da <xref:System.Object>.|  
|`public string ToString()`|Restituisce la rappresentazione di stringa dell'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
  
## <a name="events"></a>Eventi  
  
|Evento|Descrizione|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Si verifica quando un'eccezione viene serializzata per creare un oggetto di stato eccezione contenente i dati serializzati relativi all'eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
  
## <a name="usage-details"></a>Dettagli sull'uso  
 L'eccezione `MissingInteropDataException` viene generata quando una chiamata al metodo a un componente COM o Windows Runtime non riesce perché non sono disponibili le informazioni sul tipo.  
  
 I metadati disponibili in un'app al runtime sono definiti dal file di direttive di runtime (configurazione XML), *.rd.xml. Per evitare che l'app generi questa eccezione, è necessario modificare il file per definire i metadati che devono essere presenti al runtime. In genere questo errore viene risolto aggiungendo un attributo `MarshalObject`, `MarshalDelegate` o `MarshalStructure` all'elemento di programma appropriato nel file di direttive di runtime. Per informazioni sul formato di questo file, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
> [!IMPORTANT]
>  L'eccezione indica che i metadati richiesti dall'applicazione non sono disponibili in fase di esecuzione. Per questo motivo, l'eccezione non va gestita in un blocco `try`/`catch`. È invece necessario diagnosticare la causa dell'eccezione ed eliminarla usando una voce adatta a un file di direttive di runtime.  
  
 La classe `MissingInteropDataException` contiene un solo membro univoco, la proprietà `MissingType`, che indica il tipo di cui sono richiesti i metadati affinché riesca la chiamata al metodo. Tutti gli altri membri sono ereditati dalla classe base, <xref:System.Exception?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Exception?displayProperty=nameWithType>  
 [Classe MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)  
 [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
