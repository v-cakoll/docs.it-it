---
title: Cenni preliminari sulla libreria di classi .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- classes [.NET Framework], library overview
- class objects value type
- naming conventions [.NET Framework]
- types, .NET Framework
- user-defined types
- Visual Basic, data types
- data types [.NET Framework], C++
- Visual C#, data types
- libraries, .NET Framework class library
- data types [.NET Framework], JScript
- System namespace
- JScript, data types
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
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b88c85eaeabc7fa87b483c7302bd5e135e3fd276
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="net-framework-class-library-overview"></a>Cenni preliminari sulla libreria di classi .NET Framework
[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] include classi, interfacce e tipi di valore che consentono di ottimizzare il processo di sviluppo rendendolo più rapido e che forniscono accesso alle funzionalità di sistema. Per facilitare l'interoperabilità tra i linguaggi, la maggior parte dei tipi .NET Framework è compatibile con la specifica CLS (Common Language Specification) e può pertanto essere utilizzata da qualsiasi linguaggio di programmazione dotato di compilatore conforme a tale specifica.  
  
 I tipi di .NET Framework rappresentano gli elementi fondamentali per la compilazione di applicazioni, componenti e controlli .NET. In [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] sono inclusi tipi che consentono di eseguire le funzioni seguenti:  
  
-   Rappresentare tipi di dati ed eccezioni di base.  
  
-   Incapsulare strutture di dati.  
  
-   Eseguire I/O.  
  
-   Accedere a informazioni su tipi caricati.  
  
-   Richiamare i controlli di sicurezza di .NET Framework.  
  
-   Offrire l'accesso ai dati, un'elaborata interfaccia GUI (Graphical User Interface, interfaccia grafica utente) per il lato client e una GUI per il lato client controllata dal server.  
  
 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] offre una vasta gamma di interfacce, nonché di classi astratte e concrete (non astratte). È possibile utilizzare le classi concrete così come sono oppure, in molti casi, derivare da esse classi personalizzate. Per avvalersi delle funzionalità di un'interfaccia è possibile creare, oppure derivare da una delle classi di .NET Framework, una classe che consenta di implementare l'interfaccia.  
  
## <a name="naming-conventions"></a>Convenzioni di denominazione  
 Nei tipi di .NET Framework è utilizzato uno schema di denominazione con sintassi a punti che definisce una gerarchia. Secondo questa tecnica i tipi correlati vengono raggruppati in spazi dei nomi, in modo da semplificarne le ricerche e i riferimenti. La prima parte del nome completo, fino al primo punto da destra, è il nome dello spazio dei nomi. L'ultima parte del nome è il nome del tipo. **System.Collections.ArrayList**, ad esempio, rappresenta il tipo **ArrayList** appartenente allo spazio dei nomi **System.Collections**. I tipi di **System.Collections** possono essere usati per manipolare raccolte di oggetti.  
  
 Questo schema di denominazione è vantaggioso per gli sviluppatori di librerie che desiderano estendere [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] poiché consente di creare gruppi gerarchici di tipi e denominarli in modo coerente utilizzando nomi di immediata comprensione. Consente inoltre l'identificazione non ambigua dei tipi mediante il relativo nome completo, ovvero mediante il relativo spazio dei nomi e nome di tipo, in modo da evitare conflitti tra i nomi di tipo. Nella denominazione degli spazi dei nomi è opportuno che gli sviluppatori di librerie rispettino la seguente convenzione:  
  
 *NomeSocietà*.*NomeTecnologia*  
  
 Lo spazio dei nomi Microsoft.Word, ad esempio, è conforme a questa convenzione.  
  
 Il ricorso a schemi di denominazione per raggruppare dei tipi correlati all'intero di spazi dei nomi è un metodo estremamente utile per compilare e documentare librerie di classi. Questo schema di denominazione non ha tuttavia alcun effetto sulla visibilità, sull'accesso ai membri, sull'ereditarietà, sulla sicurezza o sull'associazione. Gli spazi dei nomi possono essere ripartiti tra più assembly e un singolo assembly può contenere tipi provenienti da spazi dei nomi differenti. L'assembly fornisce la struttura formale per la creazione di versioni successive, la distribuzione, la sicurezza, il caricamento e la visibilità in Common Language Runtime.  
  
 Per altre informazioni sugli spazi dei nomi e sui nomi dei tipi, vedere [Common Type System](../../docs/standard/base-types/common-type-system.md).  
  
## <a name="system-namespace"></a>Spazio dei nomi System  
 Lo spazio dei nomi <xref:System> è lo spazio dei nomi di primo livello per i tipi fondamentali di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]. Questo spazio dei nomi include classi che rappresentano i tipi di dati di base utilizzati da tutte le applicazioni: <xref:System.Object> (il primo livello della gerarchia di ereditarietà), <xref:System.Byte>, <xref:System.Char>, <xref:System.Array>, <xref:System.Int32>, <xref:System.String> e così via. Molti di questi tipi corrispondono ai tipi di dati primitivi utilizzati dal linguaggio di programmazione. Quando si scrive il codice utilizzando tipi di .NET Framework è possibile utilizzare la corrispondente parola chiave del linguaggio utilizzato dove è previsto un tipo di dati di base di .NET Framework.  
  
 Nella tabella riportata di seguito sono elencati i tipi di base disponibili in [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] con una breve descrizione di ciascun tipo e viene inoltre indicato il tipo corrispondente in Visual Basic, C#, C++ e JScript.  
  
|Categoria|Nome di classe|Descrizione|Tipo di dati di Visual Basic|Tipo di dati di C#|Tipo di dati C++|Tipo di dati di JScript|  
|--------------|----------------|-----------------|----------------------------|-------------------|---------------------|-----------------------|  
|Integer|<xref:System.Byte>|Intero senza segno a 8 bit.|**Byte**|**byte**|**unsigned char**|**Byte**|  
||<xref:System.SByte>|Intero con segno a 8 bit.<br /><br /> Non conforme a CLS.|**SByte**|**sbyte**|**char**<br /><br /> -oppure-<br /><br /> **signed** **char**|**SByte**|  
||<xref:System.Int16>|Intero con segno a 16 bit.|**Short**|**short**|**short**|**short**|  
||<xref:System.Int32>|Intero con segno a 32 bit.|**Integer**|**int**|**int**<br /><br /> -oppure-<br /><br /> **long**|**int**|  
||<xref:System.Int64>|Intero con segno a 64 bit.|**Long**|**long**|**__int64**|**long**|  
||<xref:System.UInt16>|Intero senza segno a 16 bit.<br /><br /> Non conforme a CLS.|**UShort**|**ushort**|**unsigned short**|**UInt16**|  
||<xref:System.UInt32>|Intero senza segno a 32 bit.<br /><br /> Non conforme a CLS.|**UInteger**|**uint**|**unsigned int**<br /><br /> -oppure-<br /><br /> **unsigned long**|**UInt32**|  
||<xref:System.UInt64>|Intero senza segno a 64 bit.<br /><br /> Non conforme a CLS.|**ULong**|**ulong**|**unsigned __int64**|**UInt64**|  
|Virgola mobile|<xref:System.Single>|Un numero a virgola mobile e precisione singola a 32 bit.|**Single**|**float**|**float**|**float**|  
||<xref:System.Double>|Un numero a virgola mobile e precisione doppia a 64 bit.|**Double**|**double**|**double**|**double**|  
|Logica|<xref:System.Boolean>|Un valore Boolean (true o false).|**Boolean**|**bool**|**bool**|**bool**|  
|Altro|<xref:System.Char>|Un carattere Unicode a 16 bit.|**Char**|**char**|**wchar_t**|**char**|  
||<xref:System.Decimal>|Un valore decimale a 128 bit.|**Decimal**|**decimal**|**Decimal**|**Decimal**|  
||<xref:System.IntPtr>|Un intero con segno la cui dimensione dipende dalla piattaforma sottostante (un valore a 32 bit su una piattaforma a 32 bit e un valore a 64 bit su una piattaforma a 64 bit).|**IntPtr**<br /><br /> Nessun tipo incorporato.|**IntPtr**<br /><br /> Nessun tipo incorporato.|**IntPtr**<br /><br /> Nessun tipo incorporato.|**IntPtr**|  
||<xref:System.UIntPtr>|Un intero senza segno la cui dimensione dipende dalla piattaforma sottostante (un valore a 32 bit su una piattaforma a 32 bit e un valore a 64 bit su una piattaforma a 64 bit).<br /><br /> Non conforme a CLS.|**UIntPtr**<br /><br /> Nessun tipo incorporato.|**UIntPtr**<br /><br /> Nessun tipo incorporato.|**UIntPtr**<br /><br /> Nessun tipo incorporato.|**UIntPtr**|  
Oggetti ass|<xref:System.Object>|Il primo livello della gerarchia di oggetti.|**Oggetto**|**object**|**Oggetto\***|**Oggetto**|  
||<xref:System.String>|Una stringa di caratteri Unicode immutabile e a lunghezza fissa.|**String**|**string**|**String\***|**String**|  
  
 Oltre ai tipi di dati di base, lo spazio dei nomi <xref:System> contiene oltre 100 classi, da quelle che gestiscono le eccezioni a quelle correlate a concetti fondamentali della fase di esecuzione, quali i domini di applicazione e Garbage Collector. Lo spazio dei nomi <xref:System> contiene inoltre numerosi spazi dei nomi di secondo livello.  
  
 Per altre informazioni sugli spazi dei nomi, esplorare la [libreria di classi .NET Framework](http://go.microsoft.com/fwlink/?LinkID=227195). Nella documentazione di riferimento viene fornita una breve panoramica di ciascuno spazio dei nomi nonché una descrizione formale di ogni tipo e dei relativi membri.  
  
## <a name="see-also"></a>Vedere anche  
 [Common Type System](../../docs/standard/base-types/common-type-system.md)   
 [Libreria di classi .NET Framework](http://go.microsoft.com/fwlink/?LinkID=227195)   
 [Panoramica](../../docs/framework/get-started/overview.md)

