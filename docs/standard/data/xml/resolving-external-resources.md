---
title: Risoluzione di risorse esterne
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad3fa320-4b8f-4e5c-b549-01157591007a
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 824a35ee5d4ecafc45167ff3f4bc89802af4ed96
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="resolving-external-resources"></a>Risoluzione di risorse esterne
Il **XmlResolver** proprietà del **XmlDocument** viene utilizzato il **XmlDocument** per individuare le risorse non inline nei dati XML, ad esempio il tipo di documento esterno DTD, entità e schemi. Questi elementi possono trovarsi in una rete o in un'unità locale ed essere identificati tramite un URI (Uniform Resource Identifier) . In questo modo il **XmlDocument** risolvere **EntityReference** nodi presenti nel documento e convalidare il documento in base alla DTD esterna o schema.  
  
## <a name="fully-trusted-xmldocument"></a>XmlDocument completamente attendibile  
 Il **XmlResolver** proprietà influisce sulla funzionalità del **XmlDocument. Load** metodo. Nella tabella seguente viene illustrato come la **XmlDocument. XmlResolver** proprietà viene utilizzata quando il **XmlDocument** oggetto è completamente attendibile. La tabella seguente mostra il **XmlDocument. Load** metodi quando l'input di Load è un **TextReader**, **stringa**, **flusso**, o  **URI**. Questa tabella non è applicabile per il **carico** metodo se il **XmlDocument** viene caricato da un **XmlReader**.  
  
|XmlResolver, proprietà|Funzione|Note|  
|--------------------------|--------------|-----------|  
|La proprietà è impostata su un **XmlResolver** classe che è stato creato in precedenza e con proprietà già impostate dall'utente.|Il **XmlDocument** utilizza il **XmlResolver** assegnato per risolvere i nomi di file, per risolvere i riferimenti a risorse esterne, quali DTD, entità e schemi.<br /><br /> Il **XmlResolver** viene utilizzato anche quando si risolvono risorse esterne che sono necessari quando si aggiunge o modifica di nodi nel **XmlDocument**.|Il **XmlResolver** assegnato il **XmlDocument** è il sistema di risoluzione che viene utilizzato quando è necessario individuare e risolvere risorse esterne.|  
|La proprietà è impostata su **null** (**nulla** in Microsoft Visual Basic .NET).|Non sono supportate le funzionalità che richiedono una risorsa esterna, ad esempio l'individuazione di uno schema o una DTD esterna. Le entità esterne non verranno risolte e non è supportata la modifica delle funzioni, come l'inserimento di nodi di entità che richiedono la risoluzione.|Il **XmlDocument** carica i file come anonimi e non tenta di risolvere altre risorse.|  
|La proprietà non viene impostata, ma rimane nello stato predefinito.|Un **XmlUrlResolver** con NULL credenziali verranno creata un'istanza e utilizzate dal **XmlDocument** durante la risoluzione di nomi di file, l'individuazione delle DTD, entità e schemi esterni e **null** credenziali vengono utilizzate per la modifica dei nodi.||  
  
 Nella tabella seguente vengono la **XmlDocument. Load** metodo quando l'input per il **carico** è un **XmlReader** e **XmlDocument** è completamente attendibile.  
  
|XmlResolver, proprietà|Funzione|Note|  
|--------------------------|--------------|-----------|  
|Il **XmlResolver** classe utilizzata per la **XmlDocument** è la stessa classe utilizzata dal **XmlReader**.|Il **XmlDocument** utilizza il **XmlResolver** assegnato al **XmlReader**.<br /><br /> Il **XmlDocument. resolver** proprietà non può essere impostato, indipendentemente dal **XmlDocument** trustLevel, poiché Ottiene un **XmlResolver** dal  **XmlReader**. È possibile eseguire l'override le impostazioni del **XmlResolver**' **XmlResolver** impostando il **XmlResolver** proprietà del **XmlDocument**.|Il **XmlReader** può essere il **XmlTextReader**, **XmlValidatingReader**, o un lettore personalizzato. Se il lettore usato supporta la risoluzione di entità, le entità esterne vengono risolte. I riferimenti alle entità non vengono risolti se il lettore passato non li supporta.|  
  
## <a name="semi-trusted-xmldocument"></a>XmlDocument semi-trusted  
 La tabella seguente mostra come **XmlDocument. XmlResolver** proprietà viene utilizzata quando l'oggetto è semi-trusted. Questa tabella si applica al **XmlDocument. Load** metodi quando l'input di Load è un **TextReader**, **stringa**, **flusso**, o  **URI**. Questa tabella non è applicabile per il **carico** metodo se il **XmlDocument** viene caricato da un **XmlReader**.  
  
|XmlResolver, proprietà|Funzione|Note|  
|--------------------------|--------------|-----------|  
|Nello scenario semi-trusted, il **XmlResolver** proprietà non può essere impostata su un valore diverso da null.|Un **XmlUrlResolver** con **null** credenziali verranno creata un'istanza e utilizzate per il **XmlDocument** nella risoluzione dei nomi di file, l'individuazione delle DTD esterni, entità, e gli schemi e **null** credenziali vengono utilizzate per la modifica dei nodi.|Questo comportamento è identico a quello quando il **XmlResolver** proprietà non è impostata, ma rimane nello stato predefinito.<br /><br /> Il **XmlDocument** Usa autorizzazioni anonime per tutte le azioni.|  
|La proprietà è impostata su **null** (**nulla** in Microsoft Visual Basic .NET).|Non è supportata alcuna funzionalità che richiede una risorsa esterna, ad esempio l'individuazione di uno schema esterno o di una DTD. Le entità esterne non verranno risolte e non saranno supportate le funzionalità di modifica, quali l'inserimento di nodi di entità che richiedono la risoluzione.|Quando la proprietà è **null**, il comportamento è la stessa indipendentemente dal fatto che il **XmlDocument** sia completamente attendibile o semi-trusted.|  
|La proprietà non viene impostata, ma rimane nello stato predefinito.|Un **XmlUrlResolver** con **null** credenziali verranno creata un'istanza e utilizzate per il **XmlDocument** nella risoluzione dei nomi di file, l'individuazione delle DTD esterni, entità, e gli schemi e **null** credenziali vengono utilizzate per la modifica dei nodi.|Il **XmlDocument** Usa autorizzazioni anonime per tutte le azioni.|  
  
 Questa tabella si applica al **XmlDocument. Load** metodo quando l'input per il **carico** è un **XmlReader**e **XmlDocument** è semi-trusted.  
  
|XmlResolver, proprietà|Funzione|Note|  
|--------------------------|--------------|-----------|  
|Il **XmlResolver** classe utilizzata per la **XmlDocument** corrisponde a quello utilizzato dal **XmlReader**.|Il **XmlDocument** utilizza il **XmlResolver** assegnato al **XmlReader**.<br /><br /> Il **XmlDocument. resolver** proprietà non può essere impostato, indipendentemente dal **XmlDocument** trustLevel, poiché Ottiene un **XmlResolver** dal  **XmlReader**. È possibile eseguire l'override le impostazioni del **XmlResolver** **XmlResolver** impostando il **XmlResolver** proprietà del **XmlDocument**.|Il **XmlReader** può essere il **XmlTextReader**, convalida <xref:System.Xml.XmlReader>, o un lettore personalizzato. Se il lettore usato supporta la risoluzione di entità, le entità esterne vengono risolte. I riferimenti alle entità non vengono risolti se il lettore passato non li supporta.|  
  
 Impostando XmlResolver in modo che contenga le credenziali corrette sarà possibile accedere alle risorse esterne.  
  
> [!NOTE]
>  Non è possibile recuperare il **XmlResolver** proprietà. Ciò consente di impedire a un utente di riutilizzare un **XmlResolver** sulle credenziali sono state impostate. Inoltre, se un **XmlTextReader** o la convalida <xref:System.Xml.XmlReader> viene utilizzato per caricare il **XmlDocument** e **XmlDocument** possiede un resolver che è stato impostato, i resolver da questi lettori non vengono memorizzati nella cache per il **XmlDocument** dopo il **carico** fase, in quanto anche tale operazione presenta un rischio per la sicurezza.  
  
 Per altre informazioni, vedere la sezione Note della pagina di riferimento <xref:System.Xml.XmlResolver>.  
  
## <a name="see-also"></a>Vedere anche  
 [XML Document Object Model (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
