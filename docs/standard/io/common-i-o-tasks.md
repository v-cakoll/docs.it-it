---
title: Attività di I/O comuni
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- I/O, common tasks
ms.assetid: bf00c380-706a-4e38-b829-454a480629fc
ms.openlocfilehash: 01e9d6b50bd7eeafea792a772ca86a81e40dafd4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708178"
---
# <a name="common-io-tasks"></a>Attività di I/O comuni
Lo spazio dei nomi <xref:System.IO> fornisce molte classi che consentono di eseguire diverse operazioni, ad esempio la lettura e la scrittura, su file, directory e flussi. Per altre informazioni, vedere [I/O di file e di flussi](../../../docs/standard/io/index.md).  
  
## <a name="common-file-tasks"></a>Attività comuni sui file  
  
|Per eseguire questa operazione...|Vedere l'esempio riportato in questo argomento...|  
|-------------------|--------------------------------------|  
|Creare un file di testo|Metodo <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType><br /><br /> Metodo <xref:System.IO.FileInfo.CreateText%2A?displayProperty=nameWithType><br /><br /> Metodo <xref:System.IO.File.Create%2A?displayProperty=nameWithType><br /><br /> Metodo <xref:System.IO.FileInfo.Create%2A?displayProperty=nameWithType>|  
|Scrivere in un file di testo|[Procedura: Scrivere un testo in un file](../../../docs/standard/io/how-to-write-text-to-a-file.md)<br /><br /> [Procedura: Scrivere un file di testo (C++/CLI)](/cpp/dotnet/how-to-write-a-text-file-cpp-cli)|  
|Leggere da un file di testo|[Procedura: Leggere testo da un file](../../../docs/standard/io/how-to-read-text-from-a-file.md)|  
|Aggiungere testo a un file|[Procedura: Aprire e accodare un file di log](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)<br /><br /> Metodo <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType><br /><br /> Metodo <xref:System.IO.FileInfo.AppendText%2A?displayProperty=nameWithType>|  
|Rinominare o spostare un file|Metodo <xref:System.IO.File.Move%2A?displayProperty=nameWithType><br /><br /> Metodo <xref:System.IO.FileInfo.MoveTo%2A?displayProperty=nameWithType>|  
|Eliminare un file|Metodo <xref:System.IO.File.Delete%2A?displayProperty=nameWithType><br /><br /> Metodo <xref:System.IO.FileInfo.Delete%2A?displayProperty=nameWithType>|  
|Copiare un file|Metodo <xref:System.IO.File.Copy%2A?displayProperty=nameWithType><br /><br /> Metodo <xref:System.IO.FileInfo.CopyTo%2A?displayProperty=nameWithType>|  
|Ottenere la dimensione di un file|Proprietà<xref:System.IO.FileInfo.Length%2A?displayProperty=nameWithType>|  
|Ottenere gli attributi di un file|Metodo <xref:System.IO.File.GetAttributes%2A?displayProperty=nameWithType>|  
|Impostare gli attributi di un file|Metodo <xref:System.IO.File.SetAttributes%2A?displayProperty=nameWithType>|  
|Verificare se un file esiste|Metodo <xref:System.IO.File.Exists%2A?displayProperty=nameWithType>|  
|Leggere da un file binario|[Procedura: Leggere e scrivere su un file di dati appena creato](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|  
|Scrivere in un file binario|[Procedura: Leggere e scrivere su un file di dati appena creato](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|  
|Recuperare un'estensione di file|Metodo <xref:System.IO.Path.GetExtension%2A?displayProperty=nameWithType>|  
|Recuperare il percorso completo di un file|Metodo <xref:System.IO.Path.GetFullPath%2A?displayProperty=nameWithType>|  
|Recuperare il nome e l'estensione di un file da un percorso|Metodo <xref:System.IO.Path.GetFileName%2A?displayProperty=nameWithType>|  
|Cambiare l'estensione di un file|Metodo <xref:System.IO.Path.ChangeExtension%2A?displayProperty=nameWithType>|  
  
## <a name="common-directory-tasks"></a>Attività comuni sulle directory  
  
|Per eseguire questa operazione...|Vedere l'esempio riportato in questo argomento...|  
|-------------------|--------------------------------------|  
|Accedere a un file in una cartella speciale, ad esempio Documenti|[Procedura: Scrivere un testo in un file](../../../docs/standard/io/how-to-write-text-to-a-file.md)|  
|Creare una directory|Metodo <xref:System.IO.Directory.CreateDirectory%2A?displayProperty=nameWithType><br /><br /> Proprietà<xref:System.IO.FileInfo.Directory%2A?displayProperty=nameWithType>|  
|Creare una sottodirectory|Metodo <xref:System.IO.DirectoryInfo.CreateSubdirectory%2A?displayProperty=nameWithType>|  
|Rinominare o spostare una directory|Metodo <xref:System.IO.Directory.Move%2A?displayProperty=nameWithType><br /><br /> Metodo <xref:System.IO.DirectoryInfo.MoveTo%2A?displayProperty=nameWithType>|  
|Copiare una directory|[Procedura: Copiare le directory](../../../docs/standard/io/how-to-copy-directories.md)|  
|Eliminare una directory|Metodo <xref:System.IO.Directory.Delete%2A?displayProperty=nameWithType><br /><br /> Metodo <xref:System.IO.DirectoryInfo.Delete%2A?displayProperty=nameWithType>|  
|Visualizzare i file e le sottodirectory in una directory|[Procedura: Enumerare directory e file](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)|  
|Ottenere la dimensione di una directory|Classe <xref:System.IO.Directory?displayProperty=nameWithType>|  
|Verificare se una directory esiste|Metodo <xref:System.IO.Directory.Exists%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Vedere anche

- [I/O di file e di flussi](../../../docs/standard/io/index.md)
- [Composizione dei flussi](../../../docs/standard/io/composing-streams.md)
- [I/O di file asincrono](../../../docs/standard/io/asynchronous-file-i-o.md)
