---
title: Reflection e .NET Native
ms.date: 03/30/2017
ms.assetid: 91c9eae4-c641-476c-a06e-d7ce39709763
ms.openlocfilehash: 65921377be9b8bf1c2d147b384c85cbd037d15f2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128177"
---
# <a name="reflection-and-net-native"></a>Reflection e .NET Native
In .NET Framework, lo sviluppo gestito supporta la metaprogrammazione attraverso l'API di reflection. La reflection consente di controllare gli oggetti in un'applicazione, chiamare metodi su oggetti individuati tramite ispezione, generare nuovi tipi in fase di esecuzione e supporta molti altri scenari di codice dinamico. Supporta anche la serializzazione e la deserializzazione, che consente di mantenere e successivamente ripristinare i valori dei campi di un oggetto. Tutti questi scenari richiedono che il compilatore JIT just-in-time di .NET Framework generi codice nativo basato sui metadati disponibili.  
  
 Il runtime di .NET Native non include un compilatore JIT. Di conseguenza, tutto il codice nativo necessario deve essere generato in anticipo. Viene usato un set di regole euristiche per determinare quale codice deve essere generato, ma tale euristica non può coprire tutti i possibili scenari di metaprogrammazione.  È quindi necessario fornire suggerimenti per questi scenari di metaprogrammazione usando [direttive di runtime](runtime-directives-rd-xml-configuration-file-reference.md). Se il codice di implementazione o i metadati necessari non sono disponibili in fase di esecuzione, l'app genera un'eccezione [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) o [MissingInteropDataException](missinginteropdataexception-class-net-native.md). Sono disponibili due strumenti di risoluzione dei problemi che genereranno la voce appropriata per il file di direttive di runtime che elimina l'eccezione:  
  
- Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) per i tipi.  
  
- Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) per i metodi.  
  
> [!NOTE]
> Per una panoramica del processo di compilazione di .NET Native e informazioni di base sui motivi per cui è necessario un file di direttive di runtime, vedere [Compilazione e .NET Native](net-native-and-compilation.md).  
  
 Inoltre, .NET Native non consente di riflettere i membri privati della libreria di classi .NET Framework. Ad esempio, una chiamata alla proprietà <xref:System.Reflection.TypeInfo.DeclaredFields%2A?displayProperty=nameWithType> per recuperare i campi di un tipo libreria di classi di .NET Framework restituisce solo campi pubblici o protetti.  
  
 Negli argomenti seguenti sono riportate le nozioni e la documentazione necessarie a supportare la reflection e la serializzazione nelle applicazioni di riferimento:  
  
- [API basate sulla reflection](apis-that-rely-on-reflection.md)  
  
- [Riferimento all'API Reflection](net-native-reflection-api-reference.md)  
  
- [Riferimento a file di configurazione di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)  
  
## <a name="see-also"></a>Vedi anche

- [Compilazione di app con .NET Native](index.md)
- [Compilazione e .NET Native](net-native-and-compilation.md)
