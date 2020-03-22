---
title: Classi usate nel file system e nella funzionalità di I/O di file di .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- file I/O classes
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
ms.openlocfilehash: fe70f8fb655579049bb36fc324d04530259d25f2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348922"
---
# <a name="classes-used-in-net-framework-file-io-and-the-file-system-visual-basic"></a>Classi utilizzate nel file system e nella funzionalità di I/O di file di .Net Framework (Visual Basic)

Le tabelle seguenti elencano le classi comunemente usate per l'I/O di file di .NET Framework, suddivisi in classi I/O di file, classi usate per la creazione di flussi e classi usate per leggere e scrivere nei flussi.  
  
Per un elenco più completo, vedere [Panoramica della libreria di classi](../../../../standard/class-library-overview.md).  
  
## <a name="basic-io-classes-for-files-drives-and-directories"></a>Classi di I/O di base per file, unità e directory  

 La tabella seguente elenca e descrive le principali classi usate nell'I/O di file.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|<xref:System.IO.Directory?displayProperty=nameWithType>|Offre metodi statici per creare, spostare ed enumerare directory e sottodirectory.|  
|<xref:System.IO.DirectoryInfo?displayProperty=nameWithType>|Offre metodi di istanza per creare, spostare ed enumerare directory e sottodirectory.|  
|<xref:System.IO.DriveInfo?displayProperty=nameWithType>|Offre metodi di istanza per creare, spostare ed enumerare unità.|  
|<xref:System.IO.File?displayProperty=nameWithType>|Offre metodi statici per creare, copiare, eliminare, spostare e aprire file e supporta la creazione di un `FileStream`.|  
|<xref:System.IO.FileAccess?displayProperty=nameWithType>|Definisce le costanti per l'accesso in lettura, scrittura o lettura/scrittura a un file.|  
|<xref:System.IO.FileAttributes?displayProperty=nameWithType>|Offre attributi per file e directory, ad esempio `Archive`, `Hidden` e `ReadOnly`.|  
|<xref:System.IO.FileInfo?displayProperty=nameWithType>|Offre metodi statici per creare, copiare, eliminare, spostare e aprire file e supporta la creazione di un `FileStream`.|  
|<xref:System.IO.FileMode?displayProperty=nameWithType>|Controlla la modalità di apertura di un file. Questo parametro è specificato in molti costruttori per `FileStream` e `IsolatedStorageFileStream` e per i metodi `Open` di <xref:System.IO.File> e <xref:System.IO.FileInfo>.|  
|<xref:System.IO.FileShare?displayProperty=nameWithType>|Definisce le costanti per controllare il tipo di accesso che altri flussi di file possono avere sullo stesso file.|  
|<xref:System.IO.Path?displayProperty=nameWithType>|Offre metodi e proprietà per elaborare le stringhe di directory.|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>|Controlla se è possibile accedere ai file e alle cartelle definendo le autorizzazioni <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> e <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>.|  
  
## <a name="classes-used-to-create-streams"></a>Classi usate per creare flussi  

 La tabella seguente elenca e descrive le principali classi usate per creare flussi.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|<xref:System.IO.BufferedStream?displayProperty=nameWithType>|Aggiunge un livello di buffer per operazioni di lettura e scrittura in un altro flusso.|  
|<xref:System.IO.FileStream?displayProperty=nameWithType>|Supporta l'accesso casuale ai file tramite il metodo <xref:System.IO.FileStream.Seek%2A>. <xref:System.IO.FileStream> apre file simultaneamente per impostazione predefinita, ma supporta anche operazioni asincrone.|  
|<xref:System.IO.MemoryStream?displayProperty=nameWithType>|Crea un flusso il cui archivio di backup è costituito da memoria, anziché da un file.|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=nameWithType>|Offre il flusso sottostante di dati per l'accesso alla rete.|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=nameWithType>|Definisce un flusso che collega i flussi di dati alle trasformazioni crittografiche.|  
  
## <a name="classes-used-to-read-from-and-write-to-streams"></a>Classi usate per leggere e scrivere nei flussi  

 La tabella seguente illustra le classi specifiche usate per leggere e scrivere in file con flussi.  
  
|**Class**|**Descrizione**|  
|---------------|---------------------|  
|<xref:System.IO.BinaryReader?displayProperty=nameWithType>|Legge stringhe codificate e tipi di dati primitivi da <xref:System.IO.FileStream>.|  
|<xref:System.IO.BinaryWriter?displayProperty=nameWithType>|Scrive stringhe codificate e tipi di dati primitivi in <xref:System.IO.FileStream>.|  
|<xref:System.IO.StreamReader?displayProperty=nameWithType>|Legge caratteri da <xref:System.IO.FileStream> usando <xref:System.IO.StreamReader.CurrentEncoding%2A> per convertire i caratteri da e in byte. <xref:System.IO.StreamReader> ha un costruttore che prova a verificare il corretto <xref:System.IO.StreamReader.CurrentEncoding%2A> per un determinato flusso, basato sulla presenza di un preambolo specifico di <xref:System.IO.StreamReader.CurrentEncoding%2A>, ad esempio un byte order mark.|  
|<xref:System.IO.StreamWriter?displayProperty=nameWithType>|Scrive caratteri in un `FileStream`, usando <xref:System.IO.StreamWriter.Encoding%2A> per convertire i caratteri in byte.|  
|<xref:System.IO.StringReader?displayProperty=nameWithType>|Legge caratteri da un `String`. L'output può essere un flusso in qualsiasi codifica o una `String`.|  
|<xref:System.IO.StringWriter?displayProperty=nameWithType>|Scrive caratteri in una `String`. L'output può essere un flusso in qualsiasi codifica o una `String`.|  
  
## <a name="see-also"></a>Vedere anche

- [Composing Streams](../../../../standard/io/composing-streams.md)
- [I/O su file e flusso](../../../../standard/io/index.md)
- [I/O di file asincrono](../../../../standard/io/asynchronous-file-i-o.md)
- [Nozioni fondamentali sul file system e sulla funzionalità di I/O di file di .NET Framework (Visual Basic)](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)
