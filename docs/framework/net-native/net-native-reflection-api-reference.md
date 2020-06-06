---
title: Riferimento all'API Reflection di .NET Native
ms.date: 03/30/2017
ms.assetid: 0429c049-22a3-4ba1-9cc8-f6ee91e31d9c
ms.openlocfilehash: 01678ea6230a53416f213730ae6bb66e6bc057f8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128227"
---
# <a name="net-native-reflection-api-reference"></a>Riferimento all'API Reflection di .NET Native
.NET Native include tre nuovi tipi di eccezione: [System. Runtime. CompilerServices. MissingInteropDataException](missinginteropdataexception-class-net-native.md), [System. Reflection. MissingMetadataException](missingmetadataexception-class-net-native.md)e [System. Reflection. MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md). Tenere presente quanto segue sui tre tipi di eccezione:  
  
 Questi tipi sono destinati solo all'uso interno.  
 Questi tre tipi di eccezione sono per l'uso della catena di strumenti .NET Native. Le eccezioni vengono generate quando la catena di strumenti .NET Native rileva dati mancanti che non consentono la continuazione dell'esecuzione del programma.  
  
 Non gestire queste eccezioni nel codice.  
 Queste eccezioni indicano che i metadati necessari per l'applicazione sono assenti (eccezioni [MissingInteropDataException](missinginteropdataexception-class-net-native.md) e [MissingMetadataException](missingmetadataexception-class-net-native.md) ) o che non è presente il codice di implementazione necessario (eccezione [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) ). Per correggere le condizioni di eccezione, è necessario modificare un file di direttive di runtime (rd.xml) per rendere i metadati o il codice di implementazione necessari disponibili durante il runtime. Per altre informazioni, vedere [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md). Sono disponibili due strumenti di risoluzione dei problemi che forniscono le voci appropriate per il file delle direttive di runtime che eliminerà le eccezioni [MissingMetadataException](missingmetadataexception-class-net-native.md) e [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) :  
  
- Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) per i tipi.  
  
- Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) per i metodi.  
  
> [!NOTE]
> Questo riferimento documenta tre tipi di eccezione che sono univoci per .NET Native. Per la documentazione di riferimento per l'API di Reflection .NET Framework Core, vedere gli <xref:System.Reflection> <xref:System.Reflection.Context> <xref:System.Reflection.Emit> spazi dei nomi e. Per la documentazione di riferimento per le API di interoperabilità principali di .NET Framework, vedere <xref:System.Runtime.InteropServices>.  
  
## <a name="systemreflection-namespace"></a>Spazio dei nomi System.Reflection  
 Lo spazio dei nomi <xref:System.Reflection> contiene i tipi di base usati per la reflection in .NET Framework. Per .NET Native, sono inclusi anche due nuovi tipi di eccezione:  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|[MissingMetadataException](missingmetadataexception-class-net-native.md)|Eccezione generata quando la reflection viene usata per recuperare i metadati che non sono presenti.|  
|[MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)|L'eccezione generata quando i metadati per un tipo o un membro del tipo sono disponibili ma ne è stata rimossa l'implementazione.|  
  
 Per la documentazione relativa agli altri tipi in questo spazio dei nomi, vedere le pagine di riferimento di <xref:System.Reflection> nella documentazione di .NET Framework.  
  
## <a name="systemruntimecompilerservices-namespace"></a>Spazio dei nomi System.Runtime.CompilerServices  
 Lo spazio dei nomi <xref:System.Runtime.CompilerServices> include tipi progettati per l'utente da compilatori di linguaggio. Per .NET Native, include anche un nuovo tipo di eccezione:  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|[MissingInteropDataException](missinginteropdataexception-class-net-native.md)|Eccezione generata quando viene chiamato un metodo di marshalling manuale, ma i metadati per un tipo non vengono trovati dall'analisi statica o in un file di direttive di runtime.|  
  
 Per la documentazione relativa agli altri tipi in questo spazio dei nomi, vedere le pagine di riferimento di <xref:System.Runtime.CompilerServices> nella documentazione di .NET Framework.  
  
## <a name="see-also"></a>Vedi anche

- [Classe MissingInteropDataException](missinginteropdataexception-class-net-native.md)
- [Classe MissingMetadataException](missingmetadataexception-class-net-native.md)
- [Classe MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)
- [Per iniziare](getting-started-with-net-native.md)
