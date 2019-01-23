---
title: Linee guida per la progettazione di Framework
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
  - 'libraries, .NET Framework class library'
  - 'class library design guidelines [.NET Framework], about'
  - 'class library design guidelines [.NET Framework]'
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
author: KrzysztofCwalina
---
# <a name="framework-design-guidelines"></a>Linee guida per la progettazione di Framework
In questa sezione vengono fornite linee guida per la progettazione di librerie che ne estendono e interagiscono con .NET Framework. L'obiettivo è garantire agli sviluppatori di librerie API uniformità e semplicità d'uso, fornendo un modello di programmazione unificato che è indipendente dal linguaggio di programmazione usato per lo sviluppo. È consigliabile seguire queste linee guida di progettazione durante lo sviluppo di classi e componenti in grado di estendere .NET Framework. Progettazione di librerie incoerente influisce negativamente sulla produttività degli sviluppatori e, scoraggia l'adozione.  
  
 Le linee guida sono organizzate come semplici consigli con i termini `Do`, `Consider`, `Avoid`, e `Do not`. Queste indicazioni servono per consentire agli sviluppatori di librerie di classi di comprendere i compromessi tra diverse soluzioni. Potrebbero esserci situazioni in cui progettazione buona libreria richiede che si violano tali linee guida di progettazione. Questi casi devono essere rari, ed è importante avere un motivo chiaro e accattivante per la decisione.  
  
 Queste linee guida sono state estratte dal libro *linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET riutilizzabili, 2nd Edition*, Krzysztof Cwalina e Brad Abrams.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Convenzioni di denominazione](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 Vengono fornite linee guida per la denominazione degli assembly, spazi dei nomi, tipi e membri nelle librerie di classi.  
  
 [Linee guida per la progettazione di tipi](../../../docs/standard/design-guidelines/type.md)  
 Vengono fornite linee guida per l'uso di classi statiche e astratte, interfacce, enumerazioni, strutture e altri tipi.  
  
 [Linee guida di progettazione dei membri](../../../docs/standard/design-guidelines/member.md)  
 Vengono fornite linee guida per la progettazione e utilizzando le proprietà, metodi, costruttori, campi, eventi, operatori e i parametri.  
  
 [Progettazione finalizzata all'estensibilità](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 Vengono illustrati i meccanismi di estendibilità, ad esempio la creazione di sottoclassi, usando gli eventi, i membri virtuali e i callback e spiega come scegliere i meccanismi che soddisfano al meglio i requisiti del framework.  
  
 [Linee guida di progettazione delle eccezioni](../../../docs/standard/design-guidelines/exceptions.md)  
 Descrive linee guida per la progettazione, generando un'eccezione e il rilevamento di eccezioni.  
  
 [Linee guida per l'uso](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 Descrive linee guida per l'utilizzo di tipi comuni, ad esempio matrici, gli attributi e le raccolte, che supportano la serializzazione e l'overload degli operatori di uguaglianza.  
  
 [Modelli di progettazione comuni](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 Vengono fornite linee guida per la scelta e l'implementazione delle proprietà di dipendenza.  
  
 *Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*  
  
 *Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica](../../../docs/framework/get-started/overview.md)
- [Guida di orientamento a .NET Framework](https://msdn.microsoft.com/library/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)
- [Guida di sviluppo](../../../docs/framework/development-guide.md)
