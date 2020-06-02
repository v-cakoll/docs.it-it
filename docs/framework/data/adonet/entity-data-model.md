---
title: Entity Data Model
description: Il Entity Data Model descrive la struttura dei dati, indipendentemente dal formato archiviato, che risolve le problemi derivanti dall'archiviazione dei dati in molte forme.
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: c98b1f4559ef297f8b11051940fd91f5f6fa06fd
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286740"
---
# <a name="entity-data-model"></a>Entity Data Model
EDM (Entity Data Model) è un set di concetti che descrivono la struttura dei dati, indipendentemente dal form archiviato. EDM è mutuato dal modello entità-relazione descritto da Peter Chen nel 1976, ma è anche basato su tale modello di cui estende gli utilizzi tradizionali.  
  
 EDM consente di superare le difficoltà derivanti dall'archiviazione dei dati in più form. Si pensi, ad esempio, a un'azienda che archivia i dati in database relazionali, file di testo, file XML, fogli di calcolo e rapporti. Ne derivano difficoltà considerevoli nella modellazione dati, nella progettazione di applicazioni e nell'accesso ai dati. Quando si progetta un'applicazione orientata ai dati, è difficile scrivere un codice efficiente e gestibile senza sacrificare accesso ai dati, archiviazione e scalabilità efficienti. Quando la struttura dei dati è relazionale, l'accesso ai dati, l'archiviazione e la scalabilità sono molto efficienti, ma la scrittura di un codice efficiente e gestibile diventa più difficile. Quando la struttura dei dati è basata sugli oggetti, si verifica il contrario: per scrivere un codice efficiente e gestibile, è necessario rinunciare ad accesso ai dati, archiviazione e scalabilità efficienti. Anche se è possibile trovare un giusto equilibrio tra queste due condizioni, nuove difficoltà sorgono quando i dati vengono spostati da un form a un altro. Entity Data Model risolve questi problemi descrivendo la struttura dei dati in termini di entità e relazioni indipendenti da qualsiasi schema di archiviazione. In questo modo il form di dati archiviato risulta irrilevante per la progettazione e lo sviluppo di applicazioni. E, poiché le entità e le relazioni descrivono la struttura dei dati usata in un'applicazione (non nel form archiviato), possono evolvere esattamente come un'applicazione.  
  
 Un `conceptual model` è una rappresentazione specifica della struttura di dati come entità e relazioni e viene in genere definito in un linguaggio DSL che implementa i concetti del modello EDM. Conceptual [Schema Definition Language (CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec) è un esempio di un linguaggio specifico di dominio. Entità e relazioni descritte in un modello concettuale possono essere considerate come astrazioni di oggetti e associazioni in un'applicazione. In questo modo gli sviluppatori hanno la possibilità di concentrarsi sul modello concettuale senza preoccuparsi dello schema di archiviazione e di scrivere il codice avendo come obiettivo l'efficienza e la manutenibilità. Nel frattempo i progettisti dello schema di archiviazione possono concentrarsi sull'efficienza di accesso ai dati, archiviazione e scalabilità.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 Negli argomenti di questa sezione vengono descritti i concetti relativi a Entity Data Model. I linguaggi DSL che implementano EDM devono includere i concetti descritti di seguito. Si noti che il [Entity Framework ADO.NET](./ef/index.md) utilizza CSDL per definire i modelli concettuali. Per altre informazioni, vedere [CSDL Specification](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).  
  
 [Concetti chiave di Entity Data Model](entity-data-model-key-concepts.md)  
  
 [Entity Data Model: spazi dei nomi](entity-data-model-namespaces.md)  
  
 [Entity Data Model: tipi di dati primitivi](entity-data-model-primitive-data-types.md)  
  
 [Entity Data Model: ereditarietà](entity-data-model-inheritance.md)  
  
 [estremità dell'associazione](association-end.md)  
  
 [molteplicità di estremità dell'associazione](association-end-multiplicity.md)  
  
 [set di associazioni](association-set.md)  
  
 [estremità del set di associazioni](association-set-end.md)  
  
 [tipo di associazione](association-type.md)  
  
 [tipo complesso](complex-type.md)  
  
 [contenitore di entità](entity-container.md)  
  
 [chiave di entità](entity-key.md)  
  
 [set di entità](entity-set.md)  
  
 [tipo di entità](entity-type.md)  
  
 [facet](facet.md)  
  
 [proprietà di chiave esterna](foreign-key-property.md)  
  
 [funzione dichiarata dal modello](model-declared-function.md)  
  
 [funzione definita dal modello](model-defined-function.md)  
  
 [Proprietà di navigazione](navigation-property.md)  
  
 [property](property.md)  
  
 [vincolo di integrità referenziale](referential-integrity-constraint.md)  
  
## <a name="see-also"></a>Vedere anche

- [Strumenti Entity Data Model ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Panoramica sui file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Specifica CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
