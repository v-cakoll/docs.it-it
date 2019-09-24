---
title: Introduzione alle applicazioni native del cloud
description: Informazioni sul cloud-native computing
author: robvet
ms.date: 08/26/2019
ms.openlocfilehash: a99e4b5599efee8b171c48a5b17e75b9e6cd63ca
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182853"
---
# <a name="introduction-to-cloud-native-applications"></a><span data-ttu-id="93c94-103">Introduzione alle applicazioni native del cloud</span><span class="sxs-lookup"><span data-stu-id="93c94-103">Introduction to cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="93c94-104">Un altro giorno, in ufficio, a lavorare su "la prossima grande cosa".</span><span class="sxs-lookup"><span data-stu-id="93c94-104">Another day, at the office, working on "the next big thing."</span></span>

<span data-ttu-id="93c94-105">Il cellulare squilla.</span><span class="sxs-lookup"><span data-stu-id="93c94-105">Your cellphone rings.</span></span> <span data-ttu-id="93c94-106">Si tratta di un Recruiter gentile, ovvero quello che chiama due volte al giorno per i nuovi processi.</span><span class="sxs-lookup"><span data-stu-id="93c94-106">It's your friendly recruiter - the one who calls you twice a day about new jobs.</span></span>

<span data-ttu-id="93c94-107">Ma questa volta è diversa: Avvio, equità e un ampio finanziamento.</span><span class="sxs-lookup"><span data-stu-id="93c94-107">But this time it's different: Start-up, equity, and plenty of funding.</span></span>

<span data-ttu-id="93c94-108">La menzione della tecnologia cloud e all'avanguardia ti permette di inserirti sul perimetro.</span><span class="sxs-lookup"><span data-stu-id="93c94-108">The mention of the cloud and cutting-edge technology pushes you over the edge.</span></span>

<span data-ttu-id="93c94-109">È possibile procedere in modo rapido per alcune settimane e si è ora un nuovo dipendente in una sessione di progettazione che progetta un'applicazione di eCommerce principale.</span><span class="sxs-lookup"><span data-stu-id="93c94-109">Fast forward a few weeks and you're now a new employee in a design session architecting a major eCommerce application.</span></span> <span data-ttu-id="93c94-110">Verranno completati altri siti di e-commerce leader.</span><span class="sxs-lookup"><span data-stu-id="93c94-110">You're going to complete with other leading eCommerce sites.</span></span>

<span data-ttu-id="93c94-111">Come verrà compilato?</span><span class="sxs-lookup"><span data-stu-id="93c94-111">How will you build it?</span></span>

<span data-ttu-id="93c94-112">Se si seguono le linee guida degli ultimi 15 anni, probabilmente si creerà il sistema illustrato nella figura 1,1.</span><span class="sxs-lookup"><span data-stu-id="93c94-112">If you follow the guidance from past 15 years, you'll most likely build the system shown in Figure 1.1.</span></span>

![Progettazione monolitica tradizionale](./media/monolithic-design.png)

<span data-ttu-id="93c94-114">**Figura 1-1**.</span><span class="sxs-lookup"><span data-stu-id="93c94-114">**Figure 1-1**.</span></span> <span data-ttu-id="93c94-115">Progettazione monolitica tradizionale</span><span class="sxs-lookup"><span data-stu-id="93c94-115">Traditional monolithic design</span></span>

<span data-ttu-id="93c94-116">Si crea un'applicazione principale di grandi dimensioni contenente tutta la logica di dominio.</span><span class="sxs-lookup"><span data-stu-id="93c94-116">You construct a large core application containing all of your domain logic.</span></span> <span data-ttu-id="93c94-117">Sono inclusi moduli quali identità, catalogo, ordinamento e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="93c94-117">It includes modules such as Identity, Catalog, Ordering, and more.</span></span> <span data-ttu-id="93c94-118">L'app principale comunica con un database relazionale di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="93c94-118">The core app communicates with a large relational database.</span></span> <span data-ttu-id="93c94-119">Il nucleo espone la funzionalità tramite un'interfaccia HTML.</span><span class="sxs-lookup"><span data-stu-id="93c94-119">The core exposes functionality via an HTML interface.</span></span>

<span data-ttu-id="93c94-120">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="93c94-120">Congratulations!</span></span>  <span data-ttu-id="93c94-121">È stata appena creata un'applicazione monolitica.</span><span class="sxs-lookup"><span data-stu-id="93c94-121">You just created a monolithic application.</span></span>

<span data-ttu-id="93c94-122">Non è tutto negativo.</span><span class="sxs-lookup"><span data-stu-id="93c94-122">Not all is bad.</span></span> <span data-ttu-id="93c94-123">I monoliti offrono alcuni vantaggi distinti.</span><span class="sxs-lookup"><span data-stu-id="93c94-123">Monoliths offer some distinct advantages.</span></span> <span data-ttu-id="93c94-124">Ad esempio, sono semplici da...</span><span class="sxs-lookup"><span data-stu-id="93c94-124">For example, they're straightforward to...</span></span>

- <span data-ttu-id="93c94-125">build</span><span class="sxs-lookup"><span data-stu-id="93c94-125">build</span></span> 
- <span data-ttu-id="93c94-126">test</span><span class="sxs-lookup"><span data-stu-id="93c94-126">test</span></span>
- <span data-ttu-id="93c94-127">Distribuire</span><span class="sxs-lookup"><span data-stu-id="93c94-127">deploy</span></span>
- <span data-ttu-id="93c94-128">Risolvere i problemi</span><span class="sxs-lookup"><span data-stu-id="93c94-128">troubleshoot</span></span>
- <span data-ttu-id="93c94-129">scala</span><span class="sxs-lookup"><span data-stu-id="93c94-129">scale</span></span>

<span data-ttu-id="93c94-130">Molte app riuscite attualmente disponibili sono state create come Monolith.</span><span class="sxs-lookup"><span data-stu-id="93c94-130">Many successful apps that exist today were created as monoliths.</span></span> <span data-ttu-id="93c94-131">L'app è un hit e continua ad evolversi, iterazione dopo l'iterazione, aggiungendo altre funzionalità.</span><span class="sxs-lookup"><span data-stu-id="93c94-131">The app is a hit and continues to evolve, iteration after iteration, adding more and more functionality.</span></span>

<span data-ttu-id="93c94-132">A un certo punto, tuttavia, si inizia a provare a disagio.</span><span class="sxs-lookup"><span data-stu-id="93c94-132">At some point, however, you begin to feel uncomfortable.</span></span> <span data-ttu-id="93c94-133">Si perde il controllo dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="93c94-133">You find yourself losing control of the application.</span></span> <span data-ttu-id="93c94-134">Con il passare del tempo, la sensazione diventa più intensa e infine si entra in uno stato noto come **ciclo di paura**.</span><span class="sxs-lookup"><span data-stu-id="93c94-134">As time goes on, the feeling becomes more intense and you eventually enter a state known as the **Fear Cycle**.</span></span>

- <span data-ttu-id="93c94-135">L'app è diventata talmente complicata che nessuno lo riconosce.</span><span class="sxs-lookup"><span data-stu-id="93c94-135">The app has become so overwhelmingly complicated that no single person understands it.</span></span>
- <span data-ttu-id="93c94-136">Si temono di apportare modifiche. ogni modifica presenta effetti collaterali indesiderati e costosi.</span><span class="sxs-lookup"><span data-stu-id="93c94-136">You fear making changes - each change has unintended and costly side effects.</span></span>
- <span data-ttu-id="93c94-137">Le nuove funzionalità e correzioni diventano difficili da implementare e dispendiose in termini di tempo.</span><span class="sxs-lookup"><span data-stu-id="93c94-137">New features/fixes become tricky, time-consuming, and expensive to implement.</span></span>
- <span data-ttu-id="93c94-138">Ogni versione può richiedere una distribuzione completa dell'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="93c94-138">Each release as small as it may be requires a full deployment of the entire application.</span></span>
- <span data-ttu-id="93c94-139">Un componente instabile può arrestarsi in modo anomalo nell'intero sistema.</span><span class="sxs-lookup"><span data-stu-id="93c94-139">One unstable component can crash the entire system.</span></span>
- <span data-ttu-id="93c94-140">Le nuove tecnologie e i Framework non sono un'opzione.</span><span class="sxs-lookup"><span data-stu-id="93c94-140">New technologies and frameworks aren't an option.</span></span>
- <span data-ttu-id="93c94-141">È difficile implementare le metodologie di distribuzione agile.</span><span class="sxs-lookup"><span data-stu-id="93c94-141">It's difficult to implement agile delivery methodologies.</span></span>
- <span data-ttu-id="93c94-142">L'erosione dell'architettura imposta in, in quanto la codebase si deteriora con "casi speciali" senza terminazione.</span><span class="sxs-lookup"><span data-stu-id="93c94-142">Architectural erosion sets in as the code base deteriorates with never-ending "special cases."</span></span>
- <span data-ttu-id="93c94-143">I consulenti indicano di riscriverlo.</span><span class="sxs-lookup"><span data-stu-id="93c94-143">The consultants tell you to rewrite it.</span></span>

<span data-ttu-id="93c94-144">Molte organizzazioni hanno affrontato il ciclo di paure monolitico adottando un approccio nativo al cloud per la creazione di sistemi.</span><span class="sxs-lookup"><span data-stu-id="93c94-144">Many organizations have addressed the monolithic fear cycle by adopting a cloud-native approach to building systems.</span></span> <span data-ttu-id="93c94-145">La figura 1-2 Mostra lo stesso sistema creato applicando tecniche e procedure native del cloud.</span><span class="sxs-lookup"><span data-stu-id="93c94-145">Figure 1-2 shows the same system built applying cloud-native techniques and practices.</span></span>

![Progettazione nativa del cloud](./media/cloud-native-design.png)

<span data-ttu-id="93c94-147">**Figura 1-2**.</span><span class="sxs-lookup"><span data-stu-id="93c94-147">**Figure 1-2**.</span></span> <span data-ttu-id="93c94-148">Progettazione nativa del cloud</span><span class="sxs-lookup"><span data-stu-id="93c94-148">Cloud-native design</span></span>

<span data-ttu-id="93c94-149">Si noti il modo in cui l'applicazione è scomposta in un set di microservizi isolati di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="93c94-149">Note how the application is decomposed across a set of small isolated microservices.</span></span> <span data-ttu-id="93c94-150">Ogni servizio è indipendente e incapsula il proprio codice, i dati e le dipendenze.</span><span class="sxs-lookup"><span data-stu-id="93c94-150">Each service is self-contained and encapsulates its own code, data, and dependencies.</span></span> <span data-ttu-id="93c94-151">Ogni viene distribuito in un contenitore software e gestito da un agente di orchestrazione dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="93c94-151">Each is deployed in a software container and managed by a container orchestrator.</span></span> <span data-ttu-id="93c94-152">Invece di un database relazionale di grandi dimensioni, ogni servizio è proprietario del proprio archivio dati, il tipo di che varia in base alle esigenze dei dati.</span><span class="sxs-lookup"><span data-stu-id="93c94-152">Instead of a large relational database, each service owns it own datastore, the type of which vary based upon the data needs.</span></span> <span data-ttu-id="93c94-153">Si noti che alcuni servizi dipendono da un database relazionale, ma altri nei database NoSQL.</span><span class="sxs-lookup"><span data-stu-id="93c94-153">Note how some services depend on a relational database, but other on NoSQL databases.</span></span> <span data-ttu-id="93c94-154">Un servizio archivia lo stato in una cache distribuita.</span><span class="sxs-lookup"><span data-stu-id="93c94-154">One service stores its state in a distributed cache.</span></span> <span data-ttu-id="93c94-155">Si noti il modo in cui tutto il traffico viene indirizzato attraverso un servizio gateway API responsabile del routing del traffico ai servizi back-end di base e dell'applicazione di molte problematiche trasversali.</span><span class="sxs-lookup"><span data-stu-id="93c94-155">Note how all traffic routes through an API Gateway service that is responsible for routing traffic to the core back-end services  and enforcing many cross-cutting concerns.</span></span> <span data-ttu-id="93c94-156">In particolare, l'applicazione sfrutta appieno le funzionalità di scalabilità e resilienza disponibili nelle piattaforme cloud moderne.</span><span class="sxs-lookup"><span data-stu-id="93c94-156">Most importantly, the application takes full advantage of the scalability and resiliency features found in modern cloud platforms.</span></span>

### <a name="cloud-native-computing"></a><span data-ttu-id="93c94-157">Elaborazione nativa del cloud</span><span class="sxs-lookup"><span data-stu-id="93c94-157">Cloud-native computing</span></span>

<span data-ttu-id="93c94-158">OK... Abbiamo appena usato il termine "*cloud native*".</span><span class="sxs-lookup"><span data-stu-id="93c94-158">Hmm... We just used the term, "*Cloud Native*."</span></span> <span data-ttu-id="93c94-159">Il primo pensiero potrebbe essere "che cosa significa esattamente?"</span><span class="sxs-lookup"><span data-stu-id="93c94-159">You first thought might be, “What exactly does that mean?”</span></span> <span data-ttu-id="93c94-160">Un'altra parola d'altro settore inventata dai fornitori di software per commercializzare più cose? "</span><span class="sxs-lookup"><span data-stu-id="93c94-160">Another industry buzzword concocted by software vendors to market more stuff?”</span></span>

<span data-ttu-id="93c94-161">Fortunatamente è molto diverso e speriamo che questo libro consenta di convincerlo.</span><span class="sxs-lookup"><span data-stu-id="93c94-161">Fortunately it’s far different and hopefully this book will help convince you.</span></span>

<span data-ttu-id="93c94-162">Nell'arco di un breve periodo di tempo, cloud native è diventato una tendenza di guida nel settore del software.</span><span class="sxs-lookup"><span data-stu-id="93c94-162">Within a short time, cloud native has become a driving trend in the software industry.</span></span> <span data-ttu-id="93c94-163">Si tratta di un nuovo modo per considerare la creazione di sistemi complessi e di grandi dimensioni, un approccio che sfrutta appieno le moderne procedure di sviluppo del software, le tecnologie e l'infrastruttura cloud.</span><span class="sxs-lookup"><span data-stu-id="93c94-163">It’s a new way to think about building large, complex systems, an approach that takes full advantage of modern software development practices, technologies, and cloud infrastructure.</span></span> <span data-ttu-id="93c94-164">L'approccio modifica la modalità di progettazione, implementazione, distribuzione e rendere operativo dei sistemi.</span><span class="sxs-lookup"><span data-stu-id="93c94-164">The approach changes the way you design, implement, deploy, and operationalize systems.</span></span>

<span data-ttu-id="93c94-165">A differenza dell'hype continuo che guida il nostro settore, il cloud nativo è "*per il vero*".</span><span class="sxs-lookup"><span data-stu-id="93c94-165">Unlike the continuous hype that drives our industry, cloud native is “*for-real*.”</span></span> <span data-ttu-id="93c94-166">Si consideri il [cloud native Computing Foundation](https://www.cncf.io/) (CNCF), un consorzio di oltre 300 aziende principali con una carta per rendere il computer nativo dal cloud onnipresente tra tecnologie e stack cloud.</span><span class="sxs-lookup"><span data-stu-id="93c94-166">Consider the [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF), a consortium of over 300 major corporations with a charter to make cloud-native computing ubiquitous across technology and cloud stacks.</span></span> <span data-ttu-id="93c94-167">In qualità di uno dei gruppi open source più influenti, ospita molti dei progetti open source più veloci, in GitHub.</span><span class="sxs-lookup"><span data-stu-id="93c94-167">As one of the most influential open-source groups, it hosts many of the fastest-growing open source-projects in GitHub.</span></span> <span data-ttu-id="93c94-168">Sono inclusi progetti come [Kubernetes](https://kubernetes.io/), [Prometeo](https://prometheus.io/), [Helm](https://helm.sh/), [inviato](https://www.envoyproxy.io/)e [gRPC](https://grpc.io/).</span><span class="sxs-lookup"><span data-stu-id="93c94-168">They include projects such as [Kubernetes](https://kubernetes.io/), [Prometheus](https://prometheus.io/), [Helm](https://helm.sh/), [Envoy](https://www.envoyproxy.io/), and [gRPC](https://grpc.io/).</span></span>

<span data-ttu-id="93c94-169">Il CNCF promuove un ecosistema di Open Source e neutralità del fornitore.</span><span class="sxs-lookup"><span data-stu-id="93c94-169">The CNCF fosters an ecosystem of open-source and vendor-neutrality.</span></span> <span data-ttu-id="93c94-170">In seguito, vengono presentati i principi, i modelli e le procedure consigliate native del cloud, indipendenti dalla tecnologia.</span><span class="sxs-lookup"><span data-stu-id="93c94-170">Following that lead, we present cloud-native principles, patterns, and best practices that are technology agnostic.</span></span> <span data-ttu-id="93c94-171">Allo stesso tempo, verranno illustrati i servizi e l'infrastruttura disponibili nel cloud Microsoft Azure per la creazione di sistemi nativi del cloud.</span><span class="sxs-lookup"><span data-stu-id="93c94-171">At the same time, we discuss the services and infrastructure available in the Microsoft Azure cloud for constructing cloud-native systems.</span></span> 

<span data-ttu-id="93c94-172">Che cos'è esattamente il cloud nativo?</span><span class="sxs-lookup"><span data-stu-id="93c94-172">So, what exactly is Cloud Native?</span></span> <span data-ttu-id="93c94-173">Torna indietro, rilassati e ti aiuteremo a esplorare questo nuovo mondo.</span><span class="sxs-lookup"><span data-stu-id="93c94-173">Sit back, relax, and let us help you explore this new world.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="93c94-174">[Precedente](index.md)
>[Successivo](definition.md)</span><span class="sxs-lookup"><span data-stu-id="93c94-174">[Previous](index.md)
[Next](definition.md)</span></span>