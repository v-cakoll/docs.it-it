---
title: Classe MissingMetadataException (.NET Native)
ms.date: 03/30/2017
ms.assetid: 408f25c4-6d60-475c-92b1-7b52b777c6db
ms.openlocfilehash: d73d66529bc30358c946eb0a7072f0cb8910b19a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128284"
---
# <a name="missingmetadataexception-class-net-native"></a>Classe MissingMetadataException (.NET Native)

**.NET per app di Windows per Windows 10, solo .NET Native**

Eccezione generata quando la reflection viene usata per recuperare i metadati che non sono presenti.

**Spazio dei nomi:** System.Reflection

> [!IMPORTANT]
> La `MissingMetadataException` classe è destinata esclusivamente all'uso interno da parte della catena di strumenti .NET native. La classe non può essere usata in codice di terze parti ed è preferibile evitare di gestire l'eccezione nel codice dell'applicazione. Al contrario, eliminare l'eccezione aggiungendo le voci al [file delle direttive di runtime](runtime-directives-rd-xml-configuration-file-reference.md). Per altre informazioni, vedere la sezione Osservazioni.

## <a name="syntax"></a>Sintassi

[!code-csharp[ProjectN#4](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/missingmetadataexception_syntax1.cs#4)]

Si noti che la classe `MissingMetadataException` deriva da <xref:System.TypeAccessException>.

La classe `MissingMetadataException` ha i seguenti membri:

## <a name="constructors"></a>Costruttori

|Costruttore|Descrizione|
|-----------------|-----------------|
|`public MissingMetadataException()`|Inizializza una nuova istanza della classe `MissingMetadataException` usando un messaggio fornito dal sistema che descrive l'errore.<br /><br /> Questo costruttore è solo per uso interno da parte della catena di strumenti .NET Native.|
|`public MissingMetadataException(String message)`|Inizializza una nuova istanza della classe `MissingMetadataException` con un messaggio di errore specificato.<br /><br /> Questo costruttore è solo per uso interno da parte della catena di strumenti .NET Native.|

## <a name="properties"></a>Proprietà

|Proprietà|Descrizione|
|--------------|-----------------|
|`public IDictionary Data { get; }`|Ottiene una raccolta di coppie chiave/valore che forniscono informazioni definite dall'utente aggiuntive sull'eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|
|`public string HelpLink { get; set; }`|Ottiene o imposta un collegamento al file della Guida associato all'eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|
|`public int HResult { get; protected set; }`|Ottiene o imposta `HRESULT`, un valore numerico codificato assegnato a una specifica eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|
|`public Exception InnerException { get; }`|Ottiene l'eccezione che ha causato l'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|
|`public string Message { get; }`|Ottiene un messaggio che descrive l'eccezione corrente. Ereditato da <xref:System.TypeLoadException>.|
|`public string Source { get; set; }`|Ottiene o imposta il nome dell'applicazione o dell'oggetto che ha causato l'errore. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|
|`public string StackTrace { get; }`|Ottiene una rappresentazione di stringa dei frame immediati nello stack di chiamate. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|
|`public MethodBase TargetSite { get; }`|Ottiene il metodo che ha generato l'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|
|`public string TypeName { get; ]`|Ottiene il nome completo del tipo i cui metadati non sono presenti. Ereditato da <xref:System.TypeLoadException>.|

## <a name="methods"></a>Metodi

|Metodo|Descrizione|
|------------|-----------------|
|`public bool Equals(Object obj)`|Determina se l'oggetto specificato è uguale all'oggetto corrente.  Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|
|`protected void Finalize()`|Consente a un oggetto di effettuare un tentativo di liberare risorse ed eseguire altre operazioni di pulizia prima che venga recuperato da Garbage Collection. Ereditato da <xref:System.Object>.|
|`public Exception GetBaseException()`|Restituisce l'eccezione che rappresenta la causa radice di una o più eccezioni successive. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|
|`public int GetHashCode()`|Restituisce un codice hash per un'istanza `MissingMetadataException`.   Ereditato da <xref:System.Object>.|
|`public void GetObjectData(SerializationInfo info, StreamingContext context)`|Imposta un oggetto <xref:System.Runtime.Serialization.SerializationInfo> con le informazioni relative all'eccezione.  Ereditato da <xref:System.TypeLoadException>.|
|`public Type GetType()`|Ottiene il tipo di runtime dell'istanza corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|
|`protected Object MemberwiseClone()`|Crea una copia superficiale dell'oggetto corrente. Ereditato da <xref:System.Object>.|
|`public string ToString()`|Restituisce la rappresentazione di stringa dell'eccezione corrente. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|

## <a name="events"></a>Events

|Event|Descrizione|
|-----------|-----------------|
|`protected event EventHandler<SafeSerializationEventArgs> SerializeObjectState`|Si verifica quando un'eccezione viene serializzata per creare un oggetto di stato eccezione contenente i dati serializzati relativi all'eccezione. Ereditato da <xref:System.Exception?displayProperty=nameWithType>.|

## <a name="usage-details"></a>Dettagli sull'utilizzo

Eccezione `MissingMetadataException` generata quando la reflection viene usata per accedere ai metadati che non sono disponibili in un assembly.

I metadati disponibili per un'app in fase di esecuzione sono definiti dal file di direttive di runtime (configurazione XML), \* . Rd. XML. Per evitare che l'app generi questa eccezione, è necessario modificare il file \*.rd.xm per definire i metadati che devono essere presenti in fase di esecuzione. Per informazioni sul formato del file \*.rd.xml, vedere [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).

> [!IMPORTANT]
> L'eccezione indica che i metadati richiesti dall'applicazione non sono disponibili in fase di esecuzione. Per questo motivo, l'eccezione non va gestita in un blocco `try`/`catch`. È invece necessario diagnosticare la causa dell'eccezione ed eliminarla usando un file di direttive di runtime. Per ottenere la voce che è possibile aggiungere al file di direttive di runtime che elimina l'eccezione, è possibile usare uno dei due strumenti di risoluzione dei problemi:
>
> - Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) per i tipi.
> - Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) per i metodi.

La classe `MissingMetadataException` non contiene membri univoci. Tutti i membri sono ereditati dalla relativa classe base, <xref:System.TypeAccessException>.

## <a name="see-also"></a>Vedi anche

- <xref:System.Exception?displayProperty=nameWithType>
- <xref:System.TypeAccessException>
- [Classe MissingInteropDataException](missinginteropdataexception-class-net-native.md)
- [Classe MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)
- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
