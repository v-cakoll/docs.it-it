---
title: Nomi degli assembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 8f8c2c90-f15d-400e-87e7-a757e4f04d0e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 624cc6ad264f32b9a43917d9bae751f57b4421a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-names"></a>Nomi degli assembly
Il nome di un assembly viene archiviato nei metadati e ha un effetto significativo sull'ambito dell'assembly e sull'uso dell'assembly da parte di un'applicazione. Un assembly con un nome sicuro dispone di un nome completo costituito da nome, impostazioni cultura, chiave pubblica e numero di versione dell'assembly. Questo nome è spesso detto nome visualizzato. Nel caso degli assembly caricati è possibile ottenere tale nome con la proprietà <xref:System.Reflection.Assembly.FullName%2A>.  
  
 Il runtime usa queste informazioni per individuare l'assembly e distinguerlo da altri assembly con lo stesso nome. Ad esempio un assembly con il nome sicuro `myTypes` può avere il seguente nome completo:  
  
```  
myTypes, Version=1.0.1234.0, Culture=en-US, PublicKeyToken=b77a5c561934e089c, ProcessorArchitecture=msil  
```  
  
> [!NOTE]
>  In .NET Framework versione 2.0 all'identità dell'assembly viene aggiunta l'architettura del processore, per il supporto di versioni di assembly specifiche per un determinato processore. È possibile creare versioni di un assembly la cui identità differisce solo per l'architettura del processore, ad esempio versioni specifiche per processori a 32 bit o a 64 bit. L'architettura del processore non è obbligatoria per i nomi sicuri. Per altre informazioni, vedere <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A?displayProperty=nameWithType>.  
  
 In questo esempio il nome completo indica che l'assembly `myTypes` ha un nome sicuro con un token di chiave pubblica, il valore di impostazioni cultura corrispondente a Inglese (Stati Uniti) e il numero di versione 1.0.1234.0. L'architettura del processore è "msil". Ciò significa che l'assembly sarà compilato con modalità JIT (Just-In-Time) in codice a 32 bit o a 64 bit a seconda del sistema operativo e del processore.  
  
 Il codice che richiede i tipi in un assembly deve usare un nome dell'assembly completo. Questa caratteristica è detta associazione completa. L'associazione parziale che specifica solo il nome di un assembly non è consentita per il riferimento ad assembly in .NET Framework.  
  
 Tutti i riferimenti agli assembly che costituiscono .NET Framework devono contenere anche il nome dell'assembly completo. Ad esempio il riferimento all'assembly System.Data .NET Framework per la versione 1.0 includerà:  
  
```  
System.data, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
```  
  
 Si noti che la versione corrisponde al numero di versione di tutti gli assembly .NET Framework forniti con .NET Framework versione 1.0. Per gli assembly .NET Framework il valore delle impostazioni cultura è sempre neutro e la chiave pubblica è uguale a quella visualizzata nell'esempio precedente.  
  
 Ad esempio per aggiungere un riferimento assembly a un file di configurazione per configurare un listener di traccia è necessario includere il nome dell'assembly completo per l'assembly .NET Framework di sistema:  
  
```xml  
<add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
```  
  
> [!NOTE]
>  Il runtime non distingue tra maiuscole e minuscole durante l'associazione a un assembly, ma conserva le maiuscole o le maiuscole usate nel nome dell'assembly. Vari strumenti di [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] rilevano la differenza tra maiuscole e minuscole nei nomi degli assembly. Per risultati ottimali è consigliabile gestire i nomi degli assembly includendo la distinzione tra maiuscole e minuscole.  
  
## <a name="naming-application-components"></a>Assegnazione di nomi ai componenti dell'applicazione  
 Quando determina l'identità di un assembly il runtime non considera il nome file. L'identità dell'assembly, costituita da nome, versione, impostazioni cultura e nome sicuro dell'assembly, deve risultare chiara per il runtime.  
  
 Se ad esempio si dispone di un assembly con nome myAssembly.exe che fa riferimento all'assembly myAssembly.dll, quando si esegue myAssembly.exe l'associazione viene eseguita correttamente. Se tuttavia un'altra applicazione esegue myAssembly.exe usando il metodo <xref:System.AppDomain.ExecuteAssembly%2A?displayProperty=nameWithType>, quando myAssembly.exe richiede l'associazione a "myAssembly" il runtime determina che "myAssembly" è già caricato. In questo caso, myAssembly.dll non viene mai caricato. Dato che myAssembly.exe non contiene il tipo richiesto si verifica un'eccezione <xref:System.TypeLoadException>.  
  
 Per evitare questo problema assicurarsi che gli assembly che costituiscono l'applicazione non abbiano lo stesso nome oppure posizionare gli assembly con lo stesso nome in directory diverse.  
  
> [!NOTE]
>  Se si inserisce un assembly con nome sicuro nella Global Assembly Cache il nome file dell'assembly deve corrispondere al nome dell'assembly (esclusa l'estensione del nome file, ad esempio .exe o .dll). Ad esempio se il nome file di un assembly è myAssembly.dll, il nome dell'assembly deve essere myAssembly. Gli assembly privati distribuiti solo nella directory radice dell'applicazione possono avere un nome dell'assembly diverso dal nome file.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Determinare il nome completo di un assembly](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 [Creazione degli assembly](../../../docs/framework/app-domains/create-assemblies.md)  
 [Assembly con nomi sicuri](../../../docs/framework/app-domains/strong-named-assemblies.md)  
 [Global Assembly Cache](../../../docs/framework/app-domains/gac.md)  
 [Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Programmazione con gli assembly](../../../docs/framework/app-domains/programming-with-assemblies.md)
