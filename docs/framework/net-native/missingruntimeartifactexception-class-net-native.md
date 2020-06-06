---
title: Classe MissingRuntimeArtifactException (.NET Native)
ms.date: 03/30/2017
ms.assetid: d5b3d13e-689f-4584-8ba6-44f5167a8590
ms.openlocfilehash: 7a69add45202b3ad838de592fadc82a84fa0ba5d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79180977"
---
# <a name="missingruntimeartifactexception-class-net-native"></a>Classe MissingRuntimeArtifactException (.NET Native)
**.NET per app di Windows per Windows 10, solo .NET Native**  
  
 L'eccezione generata quando i metadati per un tipo o un membro del tipo sono disponibili ma ne è stata rimossa l'implementazione.  
  
 **Spazio dei nomi:** System.Reflection  
  
> [!IMPORTANT]
> La `MissingRuntimeArtifactException` classe è destinata esclusivamente all'uso interno da parte della catena di strumenti .NET native. La classe non può essere usata in codice di terze parti ed è preferibile evitare di gestire l'eccezione nel codice dell'applicazione. Al contrario, eliminare l'eccezione aggiungendo le voci al [file delle direttive di runtime](runtime-directives-rd-xml-configuration-file-reference.md). Per altre informazioni, vedere la sezione Osservazioni.  
  
## <a name="syntax"></a>Sintassi  
 [!code-csharp[ProjectN#22](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missingruntimeartifactexception_syntax1.cs#22)]  
  
 Si noti che la classe `MissingRuntimeArtifactException` deriva da <xref:System.MemberAccessException>.  
  
 La classe `MissingRuntimeArtifactException` ha i seguenti membri:  
  
## <a name="constructors"></a>Costruttori  
  
|Costruttore|Descrizione|  
|-----------------|-----------------|  
|`public MissingRuntimeArtifactException()`|Inizializza una nuova istanza della classe `MissingRuntimeArtifactException` usando un messaggio fornito dal sistema che descrive l'errore.<br /><br /> Questo costruttore è solo per uso interno da parte della catena di strumenti .NET Native.|  
|`public MissingRuntimeArtifactException(String message)`|Inizializza una nuova istanza della classe `MissingRuntimeArtifactException` con un messaggio di errore specificato.<br /><br /> Questo costruttore è solo per uso interno da parte della catena di strumenti .NET Native.|  
  
## <a name="properties"></a>Proprietà  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|`public IDictionary Data { get; }`|Ottiene una raccolta di coppie chiave/valore che forniscono informazioni definite dall'utente aggiuntive sull'eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public string HelpLink { get; set; }`|Ottiene o imposta un collegamento al file della Guida associato all'eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public int HResult { get; protected set; }`|Ottiene o imposta `HRESULT`, un valore numerico codificato assegnato a una specifica eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public Exception InnerException { get; }`|Ottiene l'eccezione che ha causato l'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public string Message { get; }`|Ottiene un messaggio che descrive l'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public string Source { get; set; }`|Ottiene o imposta il nome dell'applicazione o dell'oggetto che ha causato l'errore. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public string StackTrace { get; }`|Ottiene una rappresentazione di stringa dei frame immediati nello stack di chiamate. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public MethodBase TargetSite { get; }`|Ottiene il metodo che ha generato l'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`public bool Equals(Object obj)`|Determina se l'oggetto specificato è uguale all'oggetto corrente.  Ereditato da <xref:System.Object>.|  
|`protected void Finalize()`|Consente a un oggetto di effettuare un tentativo di liberare risorse ed eseguire altre operazioni di pulizia prima che venga recuperato da Garbage Collection. Ereditato da <xref:System.Object>.|  
|`public Exception GetBaseException()`|Restituisce l'eccezione che rappresenta la causa radice di una o più eccezioni successive. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public int GetHashCode()`|Restituisce un codice hash per un'istanza `MissingRuntimeArtifactException`.   Ereditato da <xref:System.Object>.|  
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Imposta un oggetto <xref:System.Runtime.Serialization.SerializationInfo> con le informazioni relative all'eccezione.  Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`public Type GetType()`|Ottiene il tipo di runtime dell'istanza corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
|`protected Object MemberwiseClone()`|Crea una copia superficiale dell'oggetto corrente. Ereditato da <xref:System.Object>.|  
|`public string ToString()`|Restituisce la rappresentazione di stringa dell'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
  
## <a name="events"></a>Events  
  
|Event|Descrizione|  
|-----------|-----------------|  
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Si verifica quando un'eccezione viene serializzata per creare un oggetto di stato eccezione contenente i dati serializzati relativi all'eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|  
  
## <a name="usage-details"></a>Dettagli sull'utilizzo  
 L'eccezione `MissingRuntimeArtifactException` viene generata quando si tenta di creare un'istanza di un tipo o di richiamare un membro del tipo la cui implementazione sia stata rimossa, sebbene i metadati del tipo o del membro siano presenti.  
  
 Il fatto che i metadati e il codice di implementazione per l'esecuzione dinamica di un metodo siano disponibili per un'app in fase di esecuzione è definito dal file di direttive di runtime (configurazione XML), \* . Rd. XML. Per evitare che l'app generi questa eccezione, è necessario modificare il file \*.rd.xml per assicurarsi che i metadati necessari a un tipo o a un membro del tipo siano presenti in fase di esecuzione. Per informazioni sul formato del file \*.rd.xml, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).  
  
> [!IMPORTANT]
> L'eccezione indica che il codice di implementazione richiesto dall'applicazione non è disponibile in fase di esecuzione. Per questo motivo, l'eccezione non va gestita in un blocco `try`/`catch`. È invece necessario diagnosticare la causa dell'eccezione ed eliminarla usando un file di direttive di runtime. Questa eccezione viene in genere eliminata specificando i `Activate` `Dynamic` criteri appropriati per un elemento del programma nel file di direttive di runtime ( \* file. Rd. Xml). Per ottenere la voce che è possibile aggiungere al file di direttive di runtime che elimina l'eccezione, è possibile usare uno dei due strumenti di risoluzione dei problemi:  
>
> - Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) per i tipi.  
> - Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) per i metodi.  
  
 La classe `MissingRuntimeArtifactException` non contiene membri univoci. Tutti i membri sono ereditati dalla relativa classe base, <xref:System.MemberAccessException>.  
  
## <a name="see-also"></a>Vedi anche

- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Impostazioni dei criteri della direttiva di runtime](runtime-directive-policy-settings.md)
