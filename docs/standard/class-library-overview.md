---
title: Panoramica della libreria di classi .NET
ms.date: 02/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], library overview
- classes [.NET Core], library overview
- .NET, library overview
- class objects value type
- naming conventions [.NET Framework]
- types, .NET Framework
- user-defined types
- Visual Basic, data types
- data types [.NET Framework], C++
- Visual C#, data types
- libraries, .NET Framework class library
- data types [.NET Framework], F#
- System namespace
- F#, data types
- .NET Framework, class library
- type system [.NET Framework]
- data types [.NET Framework]
- value types
- data types [.NET Framework], Visual Basic
- Common Language Specification
- namespaces [.NET Framework]
- floating point value type
- class library [.NET Framework]
- CLS
- logical value type
- .NET Framework class library, about
- built-in types
- namespaces [.NET Framework], about namespaces
- Visual C++, data types
- members [.NET Framework], type
- data types [.NET Framework], C#
- integer value type
- base types, class library
ms.assetid: 7e4c5921-955d-4b06-8709-101873acf157
ms.openlocfilehash: 596c0fd8fec8f59d977f1db445f9000df23ad5ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79400484"
---
# <a name="net-class-library-overview"></a>Panoramica della libreria di classi .NET

Le implementazioni .NET includono classi, interfacce, delegati e tipi di valore che consentono di velocizzare e ottimizzare il processo di sviluppo e di accedere alle funzionalità di sistema. Per facilitare l'interoperabilità tra i linguaggi, la maggior parte dei tipi .NET è conforme a CLS e può pertanto essere usata da qualsiasi linguaggio di programmazione dotato di compilatore conforme alle specifiche CLS.  
  
 I tipi .NET sono gli elementi fondamentali per la compilazione di applicazioni, componenti e controlli .NET. Nelle implementazioni .NET sono inclusi tipi che consentono di eseguire le funzioni seguenti:  
  
- Rappresentare tipi di dati ed eccezioni di base.  
  
- Incapsulare strutture di dati.  
  
- Eseguire I/O.  
  
- Accedere a informazioni su tipi caricati.  
  
- Richiamare i controlli di sicurezza di .NET Framework.  
  
- Offrire l'accesso ai dati, un'elaborata interfaccia GUI (Graphical User Interface, interfaccia grafica utente) per il lato client e una GUI per il lato client controllata dal server.  
  
 .NET offre una vasta gamma di interfacce, nonché di classi astratte e concrete (non astratte). È possibile utilizzare le classi concrete così come sono oppure, in molti casi, derivare da esse classi personalizzate. Per avvalersi delle funzionalità di un'interfaccia è possibile creare, oppure derivare da una delle classi di .NET, una classe che consenta di implementare l'interfaccia.  
  
## <a name="naming-conventions"></a>Convenzioni di denominazione

 Nei tipi .NET viene usato uno schema di denominazione che applica la sintassi con il punto per definire una gerarchia. Secondo questa tecnica i tipi correlati vengono raggruppati in spazi dei nomi, in modo da semplificarne le ricerche e i riferimenti. La prima parte del nome completo, fino al primo punto da destra, è il nome dello spazio dei nomi. L'ultima parte del nome è il nome del tipo. Ad esempio, `System.Collections.Generic.List<T>` rappresenta il tipo `List<T>`, che appartiene allo spazio dei nomi `System.Collections.Generic`. I tipi in <xref:System.Collections.Generic> possono essere utilizzati per lavorare con raccolte generiche.  
  
 Questo schema di denominazione rende più semplice per gli sviluppatori di librerie estendere .NET Framework per creare gruppi gerarchici di tipi e denominarli in modo coerente utilizzando nomi di immediata comprensione. Consente inoltre l'identificazione non ambigua dei tipi mediante il relativo nome completo, ovvero mediante il relativo spazio dei nomi e nome di tipo, in modo da evitare conflitti tra i nomi di tipo. Nella denominazione degli spazi dei nomi è opportuno che gli sviluppatori di librerie rispettino la seguente convenzione:  
  
 *NomeSocietà*.*NomeTecnologia*  
  
 Lo spazio dei nomi `Microsoft.Word`, ad esempio, è conforme a questa convenzione.  
  
 Il ricorso a schemi di denominazione per raggruppare dei tipi correlati all'intero di spazi dei nomi è un metodo estremamente utile per compilare e documentare librerie di classi. Questo schema di denominazione non ha tuttavia alcun effetto sulla visibilità, sull'accesso ai membri, sull'ereditarietà, sulla sicurezza o sull'associazione. Gli spazi dei nomi possono essere ripartiti tra più assembly e un singolo assembly può contenere tipi provenienti da spazi dei nomi differenti. L'assembly fornisce la struttura formale per la creazione di versioni successive, la distribuzione, la sicurezza, il caricamento e la visibilità in Common Language Runtime.  
  
 Per altre informazioni sugli spazi dei nomi e sui nomi dei tipi, vedere [Common Type System](../../docs/standard/base-types/common-type-system.md).  
  
## <a name="system-namespace"></a>spazio dei nomi di sistema

 Lo spazio dei nomi <xref:System> è lo spazio dei nomi di primo livello per i tipi fondamentali in .NET. Questo spazio dei nomi include classi che rappresentano i tipi di dati di base utilizzati da tutte le applicazioni: <xref:System.Object> (il primo livello della gerarchia di ereditarietà), <xref:System.Byte>, <xref:System.Char>, <xref:System.Array>, <xref:System.Int32>, <xref:System.String> e così via. Molti di questi tipi corrispondono ai tipi di dati primitivi utilizzati dal linguaggio di programmazione. Quando si scrive il codice utilizzando tipi di .NET Framework è possibile utilizzare la corrispondente parola chiave del linguaggio utilizzato dove è previsto un tipo di dati di base di .NET Framework.  
  
 Nella tabella riportata di seguito sono elencati i tipi di base disponibili in .NET. con una breve descrizione di ogni tipo. Viene anche indicato il tipo corrispondente in Visual Basic, C#, C++, e F#.  
  
|Category|Nome di classe|Descrizione|Tipo di dati di Visual Basic|Tipo di dati di C#|Tipo di dati C++/CLI|Tipo di dati F#|  
|--------------|----------------|-----------------|----------------------------|-------------------|---------------------|-----------------------|  
|Integer|<xref:System.Byte>|Intero senza segno a 8 bit.|**Byte**|**byte**|**unsigned char**|**byte**|  
||<xref:System.SByte>|Numero intero con segno a 8 bit.<br /><br /> Non conforme a CLS.|**Sbyte**|**sbyte**|**Char**<br /> -oppure-<br /> **signed** **char**|**sbyte**|  
||<xref:System.Int16>|Intero con segno a 16 bit.|**Breve**|**short**|**short**|**int16**|  
||<xref:System.Int32>|Intero con segno a 32 bit.|**Integer**|**Int**|**Int**<br /><br /> -oppure-<br /><br /> **Lungo**|**Int**|  
||<xref:System.Int64>|Intero con segno a 64 bit.|**Lungo**|**Lungo**|**__int64**|**int64**|  
||<xref:System.UInt16>|Numero intero non firmato a 16 bit.<br /><br /> Non conforme a CLS.|**Ushort**|**ushort**|**unsigned short**|**uint16**|  
||<xref:System.UInt32>|Intero senza segno a 32 bit.<br /><br /> Non conforme a CLS.|**UInteger**|**uint**|**int senza segno**<br /> -oppure-<br /> **long senza segno**|**uint32**|  
||<xref:System.UInt64>|Intero senza segno a 64 bit.<br /><br /> Non conforme a CLS.|**Ulong**|**Ulong**|**unsigned __int64**|**uint64**|  
|Virgola mobile|<xref:System.Single>|Un numero a virgola mobile e precisione singola a 32 bit.|**Singolo**|**Galleggiante**|**Galleggiante**|**float32**<br> o<br>**Singolo**|  
||<xref:System.Double>|Un numero a virgola mobile e precisione doppia a 64 bit.|**Doppia**|**Doppia**|**Doppia**|**Galleggiante**<br> o <br> **Doppia**|  
|Logico|<xref:System.Boolean>|Un valore Boolean (true o false).|**Boolean**|**Bool**|**Bool**|**Bool**|  
|Altri|<xref:System.Char>|Un carattere Unicode a 16 bit.|**Char**|**Char**|**wchar_t**|**Char**|  
||<xref:System.Decimal>|Un valore decimale a 128 bit.|**Decimale**|**Decimale**|**Decimale**|**Decimale**|  
||<xref:System.IntPtr>|Un intero con segno la cui dimensione dipende dalla piattaforma sottostante (un valore a 32 bit su una piattaforma a 32 bit e un valore a 64 bit su una piattaforma a 64 bit).|**IntPtr**<br /><br /> Nessun tipo incorporato.|**IntPtr**<br /><br /> Nessun tipo incorporato.|**IntPtr**<br /><br /> Nessun tipo incorporato.|**unativeint**|  
||<xref:System.UIntPtr>|Un intero senza segno la cui dimensione dipende dalla piattaforma sottostante (un valore a 32 bit su una piattaforma a 32 bit e un valore a 64 bit su una piattaforma a 64 bit).<br /><br /> Non conforme a CLS.|**UIntPtr**<br /><br /> Nessun tipo incorporato.|**UIntPtr**<br /><br /> Nessun tipo incorporato.|**UIntPtr**<br /><br /> Nessun tipo incorporato.|**unativeint**|  
||<xref:System.Object>|Il primo livello della gerarchia di oggetti.|**Oggetto**|**Oggetto**|**Oggetto:**|**obj**|  
||<xref:System.String>|Una stringa di caratteri Unicode immutabile e a lunghezza fissa.|**Stringa**|**Stringa**|**Stringa di lavoro**|**Stringa**|  
  
 Oltre ai tipi di dati di base, lo spazio dei nomi <xref:System> contiene oltre 100 classi, da quelle che gestiscono le eccezioni a quelle correlate a concetti fondamentali della fase di esecuzione, quali i domini di applicazione e Garbage Collector. Lo spazio dei nomi <xref:System> contiene inoltre numerosi spazi dei nomi di secondo livello.  
  
 Per altre informazioni sugli spazi dei nomi, usare il [Browser API .NET](https://docs.microsoft.com/dotnet/api) per esplorare la libreria di classi .NET. La documentazione di riferimento delle API contiene informazioni su ogni spazio dei nomi, sui relativi tipi e membri.  
  
## <a name="see-also"></a>Vedere anche

- [Common Type System](../../docs/standard/base-types/common-type-system.md)
- [Browser per le API .NET](../../api/index.md)
- [Panoramica](../../docs/framework/get-started/overview.md)
