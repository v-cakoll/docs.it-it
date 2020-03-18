---
title: Manifesto dell'assembly
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest
- dynamic assemblies, assembly manifest
- metadata, assembly manifest
- culture, assembly manifest
- assemblies [.NET Framework], metadata
ms.assetid: 8e40fab9-549d-4731-aec2-ffa47a382de0
ms.openlocfilehash: f1913f8c41ba4a7b54f7abcdfb97400503da8ac5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73107146"
---
# <a name="assembly-manifest"></a>Manifesto dell'assembly
Ogni assembly, sia esso statico o dinamico, include una raccolta di dati che descrivono le relazioni tra i diversi elementi che lo compongono. Tali metadati sono contenuti nel manifesto dell'assembly. Il manifesto dell'assembly contiene tutti i metadati necessari per specificare l'identità di sicurezza e i requisiti di versione dell'assembly e tutti i metadati necessari per definire l'ambito dell'assembly e risolvere i riferimenti a classi e risorse. Il manifesto dell'assembly può essere archiviato in un file PE *(exe* o *dll)* con codice MSIL (Microsoft Intermediate Language) o in un file PE autonomo contenente solo informazioni sul manifesto dell'assembly.  
  
 Nella figura che segue vengono illustrati i diversi modi in cui è possibile memorizzare il manifesto.  
  
 ![Diagramma che illustra il manifesto in una configurazione di assembly a file singolo e a più file.](./media/manifest/assembly-types-diagram.gif)  
  
 Nel caso di un assembly con un solo file associato, il manifesto viene incorporato nel file PE per formare un assembly a file singolo. È possibile creare un assembly su più file con un manifesto autonomo o con il manifesto incorporato in uno dei file PE dell'assembly.  
  
 Il manifesto dell'assembly svolge le seguenti funzioni:  
  
- Enumera i file che compongono l'assembly.  
  
- Determina in che modo i riferimenti ai tipi e alle risorse dell'assembly vengono collegati ai file che contengono le relative dichiarazioni e implementazioni.  
  
- Enumera altri assembly da cui l'assembly dipende.  
  
- Fornisce un livello di riferimenti indiretti tra i consumatori dell'assembly e i dettagli di implementazione dell'assembly.  
  
- Conferisce all'assembly la capacità di descrivere se stesso.  
  
## <a name="assembly-manifest-contents"></a>Contenuto del manifesto dell'assembly  
 Nella tabella che segue vengono mostrate le informazioni contenute nel manifesto dell'assembly. I primi quattro elementi: il nome dell'assembly, il numero di versione, le impostazioni cultura e le informazioni sul nome sicuro costituiscono l'identità dell'assembly.  
  
|Informazioni|Descrizione|  
|-----------------|-----------------|  
|Nome assembly|Una stringa di testo che specifica il nome dell'assembly.|  
|Numero di versione|Un numero di versione principale e secondario e un numero di revisione e di build. Common Language Runtime utilizza tali numeri per assicurare l'applicazione dei criteri per la gestione delle versioni.|  
|Impostazioni cultura|Informazioni sulla lingua o sulle impostazioni cultura supportate dall'assembly. Questa informazione deve essere utilizzata solo per designare un assembly come assembly satellite contenente informazioni specifiche della lingua o delle impostazioni cultura. Un assembly con informazioni relative alle impostazioni cultura viene automaticamente considerato come assembly satellite.|  
|Informazioni sul nome sicuro|La chiave pubblica rilasciata dall'editore se all'assembly è stato assegnato un nome sicuro.|  
|Elenco di tutti i file dell'assembly|Un elenco di tutti i file contenuti nell'assembly e un nome di file. Si noti che tutti i file che compongono l'assembly devono essere contenuti nella stessa directory del file che contiene il manifesto dell'assembly.|  
|Informazioni per il riferimento ai tipi|Informazioni utilizzate dal runtime per collegare il riferimento a un tipo al file che ne contiene la dichiarazione e l'implementazione. Vengono utilizzate per i tipi esportati dall'assembly.|  
|Informazioni sugli assembly a cui si fa riferimento|Un elenco di tutti gli assembly a cui questo assembly fa riferimento in modo statico. Ciascun riferimento include il nome, i metadati (versione, impostazioni cultura, sistema operativo e così via) e la chiave pubblica dell'assembly, se questo ha un nome sicuro.|  
  
 È possibile aggiungere o modificare alcune informazioni del manifesto dell'assembly utilizzando gli attributi dell'assembly nel proprio codice. È anche possibile modificare le informazioni sulla versione e alcuni attributi informativi, tra cui marchio, copyright, prodotto, società e versione informativa. Per un elenco completo degli attributi [dell'assembly, vedere Impostare gli attributi dell'assieme](set-attributes.md).  
  
## <a name="see-also"></a>Vedere anche

- [Contenuto degli assembly](contents.md)
- [Controllo delle versioni degli assembly](versioning.md)
- [Creare assembly satellite](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [Assembly con nome sicuro](strong-named.md)
