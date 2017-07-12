

# [Microservizi .NET: Architettura per le applicazioni .NET incluse in contenitori](index.md)


## [Introduzione a contenitori e Docker](container-docker-introduction/index.md)


### [Che cos'è Docker?](container-docker-introduction/docker-defined.md)


### [Terminologia di Docker](container-docker-introduction/docker-terminology.md)


### [Contenitori, immagini e registri di Docker](container-docker-introduction/docker-containers-images-registries.md)


## [Scelta di NET Core o NET Framework per i contenitori di Docker](net-core-net-framework-containers/index.md)


### [Indicazioni generali](net-core-net-framework-containers/general-guidance.md)


### [Quando scegliere .NET Core per i contenitori di Docker](net-core-net-framework-containers/net-core-container-scenarios.md)


### [Quando scegliere .NET Framework per i contenitori di Docker](net-core-net-framework-containers/net-framework-container-scenarios.md)


### [Tabella decisioni: le versioni di .NET Framework da usare per Docker](net-core-net-framework-containers/container-framework-choice-factors.md)


### [Sistema operativo di destinazione per i contenitori .NET](net-core-net-framework-containers/net-container-os-targets.md)


### [Immagini Docker .NET ufficiale](net-core-net-framework-containers/official-net-docker-images.md)


## [Architettura di applicazioni basate su contenitori e microservizi](architect-microservice-container-applications/index.md)


### [Inserimento di applicazioni monolitiche nei contenitori](architect-microservice-container-applications/containerize-monolithic-applications.md)


### [Stato e dati nelle applicazioni di Docker](architect-microservice-container-applications/docker-application-state-data.md)


### [Architettura orientata ai servizi](architect-microservice-container-applications/service-oriented-architecture.md)


### [Architettura di microservizi](architect-microservice-container-applications/microservices-architecture.md)


### [Sovranità dei dati per microservizio](architect-microservice-container-applications/data-sovereignty-per-microservice.md)


### [Architettura logica e architettura fisica](architect-microservice-container-applications/logical-versus-physical-architecture.md)


### [Problemi e soluzioni per la gestione dei dati distribuiti](architect-microservice-container-applications/distributed-data-management.md)


### [Identificazione dei limiti del modello di dominio per ogni microservizio](architect-microservice-container-applications/identify-microservice-domain-model-boundaries.md)


### [Comunicazione tra microservizi](architect-microservice-container-applications/communication-between-microservices.md)


### [Comunicazione asincrona basata su messaggi](architect-microservice-container-applications/asynchronous-message-based-communication.md)


### [Creazione, evoluzione e controllo delle versioni di API e contratti dei microservizi](architect-microservice-container-applications/maintain-microservice-apis.md)


### [Indirizzabilità dei microservizi e registro del servizio](architect-microservice-container-applications/microservices-addressability-service-registry.md)


### [Creazione dell'interfaccia utente composita basata su microservizi, tra cui la forma visiva dell'interfaccia utente e il layout generato da più microservizi](architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md)


### [Resilienza e disponibilità elevata nei microservizi](architect-microservice-container-applications/resilient-high-availability-microservices.md)


### [Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate](architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)


### [Uso di Azure Service Fabric](architect-microservice-container-applications/using-azure-service-fabric.md)


## [Processo di sviluppo per le applicazioni basate su Docker](docker-application-development-process/index.md)


### [Flusso di lavoro di sviluppo per le app di Docker](docker-application-development-process/docker-app-development-workflow.md)


## [Distribuzione di applicazioni Web .NET Core basate su singolo contenitore in host di Linux o Windows Nano Server](net-core-single-containers-linux-windows-server-hosts/index.md)


## [Migrazione di applicazioni monolitiche .NET Framework legacy nei contenitori di Windows](containerize-net-framework-applications/index.md)


## [Progettazione e sviluppo di applicazioni NET basate su più contenitori e microservizi](multi-container-microservice-net-applications/index.md)


### [Progettazione di un'applicazione orientata ai microservizi](multi-container-microservice-net-applications/microservice-application-design.md)


### [Creazione di un microservizio CRUD semplice basato sui dati](multi-container-microservice-net-applications/data-driven-crud-microservice.md)


### [Definizione dell'applicazione a più contenitori con docker-compose.yml](multi-container-microservice-net-applications/multi-container-applications-docker-compose.md)


### [Uso di un server di database eseguito come un contenitore](multi-container-microservice-net-applications/database-server-container.md)


### [Implementazione della comunicazione basata su eventi tra microservizi (eventi di integrazione)](multi-container-microservice-net-applications/integration-event-based-microservice-communications.md)


### [Implementazione di un bus di eventi con RabbitMQ per l'ambiente di sviluppo o test](multi-container-microservice-net-applications/rabbitmq-event-bus-development-test-environment.md)


### [Sottoscrizione di eventi](multi-container-microservice-net-applications/subscribe-events.md)


### [Test delle app Web e dei servizi ASP.NET di base](multi-container-microservice-net-applications/test-aspnet-core-services-web-apps.md)


## [Gestione della complessità aziendale in un microservizio con i modelli DDD e CQRS](microservice-ddd-cqrs-patterns/index.md)


### [Applicazione di modelli CQRS e DDD semplificati in un microservizio.](microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns.md)


### [Applicazione degli approcci CQRS e CQS in un microservizio DDD in eShopOnContainers](microservice-ddd-cqrs-patterns/eshoponcontainers-cqrs-ddd-microservice.md)


### [Implementazione di letture/query in un microservizio CQRS](microservice-ddd-cqrs-patterns/cqrs-microservice-reads.md)


### [Progettazione di un microservizio orientato a DDD](microservice-ddd-cqrs-patterns/ddd-oriented-microservice.md)


### [Progettazione di un modello di dominio del microservizio](microservice-ddd-cqrs-patterns/microservice-domain-model.md)


### [Implementazione di un modello di dominio del microservizio con .NET Core](microservice-ddd-cqrs-patterns/net-core-microservice-domain-model.md)


### [Seedwork (classi di base riutilizzabili e interfacce per il modello di dominio)](microservice-ddd-cqrs-patterns/seedwork-domain-model-base-classes-interfaces.md)


### [Implementazione di oggetti valore](microservice-ddd-cqrs-patterns/implement-value-objects.md)


### [Uso delle classi di enumerazione anziché dei tipi enum](microservice-ddd-cqrs-patterns/enumeration-classes-over-enum-types.md)


### [Progettazione di convalide nel livello del modello di dominio](microservice-ddd-cqrs-patterns/domain-model-layer-validations.md)


### [Convalida lato client (convalida nei livelli di presentazione)](microservice-ddd-cqrs-patterns/client-side-validation.md)


### [Eventi del dominio: progettazione e implementazione](microservice-ddd-cqrs-patterns/domain-events-design-implementation.md)


### [Progettazione del livello di persistenza dell'infrastruttura](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-design.md)


### [Implementazione del livello di persistenza dell'infrastruttura con Entity Framework Core](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-implemenation-entity-framework-core.md)


### [Uso dei database NoSQL come infrastruttura di persistenza](microservice-ddd-cqrs-patterns/nosql-database-persistence-infrastructure.md)


### [Progettazione del livello dell'applicazione del microservizio e dell'API Web](microservice-ddd-cqrs-patterns/microservice-application-layer-web-api-design.md)


### [Implementazione del livello dell'applicazione del microservizio usando l'API Web](microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)


## [Implementazione di applicazioni resilienti](implement-resilient-applications/index.md)


### [Gestione degli errori parziali](implement-resilient-applications/handle-partial-failure.md)


### [Strategie di gestione degli errori parziali](implement-resilient-applications/partial-failure-strategies.md)


### [Implementazione di tentativi con backoff esponenziale](implement-resilient-applications/implement-retries-exponential-backoff.md)


### [Implementazione di connessioni SQL resilienti di Entity Framework Core](implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md)


### [Implementazione di tentativi di chiamata HTTP personalizzati con backoff esponenziale](implement-resilient-applications/implement-custom-http-call-retries-exponential-backoff.md)


### [Implementazione di tentativi di chiamata HTTP con backoff esponenziale con Polly](implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md)


### [Implementazione dello schema di interruttori](implement-resilient-applications/implement-circuit-breaker-pattern.md)


### [Monitoraggio dell'integrità](implement-resilient-applications/monitor-app-health.md)


## [Protezione di microservizi e applicazioni Web .NET](secure-net-microservices-web-applications/index.md)


### [Informazioni sull'autorizzazione in applicazioni Web e microservizi .NET](secure-net-microservices-web-applications/authorization-net-microservices-web-applications.md)


### [Archiviazione sicura dei segreti dell'applicazione durante lo sviluppo](secure-net-microservices-web-applications/developer-app-secrets-storage.md)


### [Uso dell'insieme di credenziali delle chiavi di Azure per proteggere i segreti in fase di produzione](secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)


## [Principali considerazioni](key-takeaways.md)
