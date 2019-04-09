---
title: Entity Data Model
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: 8e96890d97f652295a3fdb67c48ec37710280eec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197919"
---
# <a name="entity-data-model"></a>Entity Data Model
EDM (Entity Data Model) è un set di concetti che descrivono la struttura dei dati, indipendentemente dal form archiviato. EDM è mutuato dal modello entità-relazione descritto da Peter Chen nel 1976, ma è anche basato su tale modello di cui estende gli utilizzi tradizionali.  
  
 EDM consente di superare le difficoltà derivanti dall'archiviazione dei dati in più form. Si pensi, ad esempio, a un'azienda che archivia i dati in database relazionali, file di testo, file XML, fogli di calcolo e rapporti. Ne derivano difficoltà considerevoli nella modellazione dati, nella progettazione di applicazioni e nell'accesso ai dati. Quando si progetta un'applicazione orientata ai dati, è difficile scrivere un codice efficiente e gestibile senza sacrificare accesso ai dati, archiviazione e scalabilità efficienti. Quando la struttura dei dati è relazionale, l'accesso ai dati, l'archiviazione e la scalabilità sono molto efficienti, ma la scrittura di un codice efficiente e gestibile diventa più difficile. Quando i dati hanno una struttura di oggetti, vengono invertiti i compromessi: La scrittura di codice efficiente e gestibile comporta il costo di scalabilità, archiviazione e accesso efficiente ai dati. Anche se è possibile trovare un giusto equilibrio tra queste due condizioni, nuove difficoltà sorgono quando i dati vengono spostati da un form a un altro. Entity Data Model risolve questi problemi descrivendo la struttura dei dati in termini di entità e relazioni indipendenti da qualsiasi schema di archiviazione. In questo modo il form di dati archiviato risulta irrilevante per la progettazione e lo sviluppo di applicazioni. E, poiché le entità e le relazioni descrivono la struttura dei dati usata in un'applicazione (non nel form archiviato), possono evolvere esattamente come un'applicazione.  
  
 Un `conceptual model` è una rappresentazione specifica della struttura di dati come entità e relazioni e viene in genere definito in un linguaggio DSL che implementa i concetti del modello EDM. [Linguaggio di definizione schema concettuale (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) è riportato un esempio di questo tipo un linguaggio specifico di dominio. Entità e relazioni descritte in un modello concettuale possono essere considerate come astrazioni di oggetti e associazioni in un'applicazione. In questo modo gli sviluppatori hanno la possibilità di concentrarsi sul modello concettuale senza preoccuparsi dello schema di archiviazione e di scrivere il codice avendo come obiettivo l'efficienza e la manutenibilità. Nel frattempo i progettisti dello schema di archiviazione possono concentrarsi sull'efficienza di accesso ai dati, archiviazione e scalabilità.  
  
## <a name="in-this-section"></a>In questa sezione  
 Negli argomenti di questa sezione vengono descritti i concetti relativi a Entity Data Model. I linguaggi DSL che implementano EDM devono includere i concetti descritti di seguito. Si noti che il [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Usa CSDL per definire i modelli concettuali. Per altre informazioni, vedere [CSDL Specification](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).  
  
 [Concetti chiave di Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [Entity Data Model: Spazi dei nomi](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [Entity Data Model: tipi di dati primitivi](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [Entity Data Model: Ereditarietà](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [entità finale dell'associazione](../../../../docs/framework/data/adonet/association-end.md)  
  
 [molteplicità di entità finale dell'associazione](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [set di associazioni](../../../../docs/framework/data/adonet/association-set.md)  
  
 [entità finale del set di associazioni](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [tipo di associazione](../../../../docs/framework/data/adonet/association-type.md)  
  
 [tipo complesso](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [contenitore di entità](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [chiave di entità](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [set di entità](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [tipo di entità](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [facet](../../../../docs/framework/data/adonet/facet.md)  
  
 [proprietà di chiave esterna](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [funzione dichiarata dal modello](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [funzione definita dal modello](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [proprietà di navigazione](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [proprietà](../../../../docs/framework/data/adonet/property.md)  
  
 [vincolo di integrità referenziale](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a>Vedere anche

- [Strumenti di ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Panoramica sui file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Specifica CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)
