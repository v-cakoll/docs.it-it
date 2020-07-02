---
title: Guida alla distribuzione di .NET Framework per amministratori
description: Leggere la guida alla distribuzione di .NET per gli amministratori. Usare queste informazioni per distribuire .NET versione 4,5 e le relative dipendenze di sistema in una rete.
ms.date: 04/10/2018
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
ms.openlocfilehash: d58eac4f21e4f1069ac392aacb4e9818831e914c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622653"
---
# <a name="net-framework-deployment-guide-for-administrators"></a><span data-ttu-id="f7a6f-104">Guida alla distribuzione di .NET Framework per amministratori</span><span class="sxs-lookup"><span data-stu-id="f7a6f-104">.NET Framework Deployment Guide for Administrators</span></span>

<span data-ttu-id="f7a6f-105">Questo articolo dettagliato descrive come un amministratore di sistema può distribuire il .NET Framework 4,5 e le relative dipendenze di sistema attraverso una rete usando Microsoft endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-105">This step-by-step article describes how a system administrator can deploy the .NET Framework 4.5 and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="f7a6f-106">L'articolo presuppone che tutti i computer client di destinazione soddisfino i requisiti minimi per .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-106">This article assumes that all target client computers meet the minimum requirements for the .NET Framework.</span></span> <span data-ttu-id="f7a6f-107">Per un elenco dei requisiti software e hardware per l'installazione di .NET Framework 4.5, vedere [Requisiti di sistema](../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-107">For a list of the software and hardware requirements for installing the .NET Framework 4.5, see [System Requirements](../get-started/system-requirements.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f7a6f-108">Il software a cui si fa riferimento nel presente documento, inclusi, a titolo esemplificativo, i .NET Framework 4,5, Configuration Manager e Active Directory, sono soggetti a condizioni di licenza.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-108">The software referenced in this document, including, without limitation, the .NET Framework 4.5, Configuration Manager, and Active Directory, are each subject to license terms and conditions.</span></span> <span data-ttu-id="f7a6f-109">Queste istruzioni presuppongono che tali condizioni di licenza siano state riviste e accettate dai licenziatari del software</span><span class="sxs-lookup"><span data-stu-id="f7a6f-109">These instructions assume that such license terms and conditions have been reviewed and accepted by the appropriate licensees of the software.</span></span> <span data-ttu-id="f7a6f-110">e non derogano ad alcuna condizione di tali contratti di licenza.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-110">These instructions do not waive any of the terms and conditions of such license agreements.</span></span>
>
> <span data-ttu-id="f7a6f-111">Per informazioni sul supporto per la .NET Framework, vedere [.NET Framework i criteri di supporto ufficiale](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) nel sito web di supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-111">For information about support for the .NET Framework, see [.NET Framework official support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework) on the Microsoft Support website.</span></span>

<span data-ttu-id="f7a6f-112">In questo argomento sono incluse le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7a6f-112">This topic contains the following sections:</span></span>

- [<span data-ttu-id="f7a6f-113">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="f7a6f-113">The deployment process</span></span>](#the_deployment_process)
- [<span data-ttu-id="f7a6f-114">Distribuzione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f7a6f-114">Deploying the .NET Framework</span></span>](#deploying_in_a_test_environment)
- [<span data-ttu-id="f7a6f-115">Creare una raccolta</span><span class="sxs-lookup"><span data-stu-id="f7a6f-115">Create a collection</span></span>](#creating_a_collection)
- [<span data-ttu-id="f7a6f-116">Creare un pacchetto e un programma</span><span class="sxs-lookup"><span data-stu-id="f7a6f-116">Create a package and program</span></span>](#creating_a_package)
- [<span data-ttu-id="f7a6f-117">Selezionare un punto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="f7a6f-117">Select a distribution point</span></span>](#select_dist_point)
- [<span data-ttu-id="f7a6f-118">Distribuire il pacchetto</span><span class="sxs-lookup"><span data-stu-id="f7a6f-118">Deploy the package</span></span>](#deploying_package)
- [<span data-ttu-id="f7a6f-119">Risorse</span><span class="sxs-lookup"><span data-stu-id="f7a6f-119">Resources</span></span>](#resources)
- [<span data-ttu-id="f7a6f-120">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="f7a6f-120">Troubleshooting</span></span>](#troubleshooting)

<a name="the_deployment_process"></a>

## <a name="the-deployment-process"></a><span data-ttu-id="f7a6f-121">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="f7a6f-121">The deployment process</span></span>

<span data-ttu-id="f7a6f-122">Quando si dispone dell'infrastruttura di supporto sul posto, è possibile utilizzare Configuration Manager per distribuire il pacchetto ridistribuibile di .NET Framework nei computer della rete.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-122">When you have the supporting infrastructure in place, you use Configuration Manager to deploy the .NET Framework redistributable package to computers on the network.</span></span> <span data-ttu-id="f7a6f-123">La creazione dell'infrastruttura include la creazione e la definizione di cinque aree primarie: raccolte, un pacchetto e un programma per il software, punti di distribuzione e distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-123">Building the infrastructure involves creating and defining five primary areas: collections, a package and program for the software, distribution points, and deployments.</span></span>

- <span data-ttu-id="f7a6f-124">Le **raccolte** sono gruppi di risorse di Configuration Manager, ad esempio utenti, gruppi di utenti o computer, ai quali viene distribuito .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-124">**Collections** are groups of Configuration Manager resources, such as users, user groups, or computers, to which the .NET Framework is deployed.</span></span> <span data-ttu-id="f7a6f-125">Per ulteriori informazioni, vedere [Introduzione alle raccolte in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) nella libreria della documentazione di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-125">For more information, see [Introduction to collections in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="f7a6f-126">I **pacchetti e programmi** in genere rappresentano le applicazioni software da installare in un computer client, ma possono anche contenere singoli file, aggiornamenti o persino singoli comandi.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-126">**Packages and programs** typically represent software applications to be installed on a client computer, but they might also contain individual files, updates, or even individual commands.</span></span> <span data-ttu-id="f7a6f-127">Per ulteriori informazioni, vedere [pacchetti e programmi in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs) nella libreria della documentazione di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-127">For more information, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="f7a6f-128">I **punti di distribuzione** sono ruoli di sistema dei siti di Configuration Manager nei quali sono archiviati i file necessari per l'esecuzione del software nei computer client.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-128">**Distribution points** are Configuration Manager site system roles that store files required for software to run on client computers.</span></span> <span data-ttu-id="f7a6f-129">Quando il client di Configuration Manager riceve ed elabora una distribuzione software, contatta un punto di distribuzione per scaricare il contenuto associato al software e avviare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-129">When the Configuration Manager client receives and processes a software deployment, it contacts a distribution point to download the content associated with the software and to start the installation process.</span></span> <span data-ttu-id="f7a6f-130">Per altre informazioni, vedere [Concetti di base della gestione dei contenuti in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management) nella raccolta di documentazione di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-130">For more information, see [Fundamental concepts for content management in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management) in the Configuration Manager documentation library.</span></span>

- <span data-ttu-id="f7a6f-131">Le **distribuzioni** indicano ai membri validi della raccolta di destinazione specificata di installare il pacchetto software.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-131">**Deployments** instruct applicable members of the specified target collection to install the software package.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7a6f-132">Le procedure descritte in questo argomento includono impostazioni standard per creare e distribuire un pacchetto e un programma e potrebbero non illustrare tutte le impostazioni possibili.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-132">The procedures in this topic contain typical settings for creating and deploying a package and program, and might not cover all possible settings.</span></span> <span data-ttu-id="f7a6f-133">Per altre informazioni sulle opzioni di distribuzione di Configuration Manager, vedere [Libreria della documentazione di Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682041%28v=technet.10%29).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-133">For other Configuration Manager deployment options, see the [Configuration Manager Documentation Library](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682041%28v=technet.10%29).</span></span>

<a name="deploying_in_a_test_environment"></a>

## <a name="deploying-the-net-framework"></a><span data-ttu-id="f7a6f-134">Distribuzione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f7a6f-134">Deploying the .NET Framework</span></span>

<span data-ttu-id="f7a6f-135">È possibile usare Configuration Manager per distribuire un'installazione invisibile all'utente del .NET Framework 4,5, in cui gli utenti non interagiscono con il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-135">You can use Configuration Manager to deploy a silent installation of the .NET Framework 4.5, where the users do not interact with the installation process.</span></span> <span data-ttu-id="f7a6f-136">A tale scopo, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="f7a6f-136">Follow these steps:</span></span>

1. <span data-ttu-id="f7a6f-137">[Creare una raccolta](#creating_a_collection).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-137">[Create a collection](#creating_a_collection).</span></span>

2. <span data-ttu-id="f7a6f-138">[Creare un pacchetto e un programma per il pacchetto ridistribuibile di .NET Framework](#creating_a_package).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-138">[Create a package and program for the .NET Framework redistributable](#creating_a_package).</span></span>

3. <span data-ttu-id="f7a6f-139">[Selezionare un punto di distribuzione](#select_dist_point).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-139">[Select a distribution point](#select_dist_point).</span></span>

4. <span data-ttu-id="f7a6f-140">[Distribuire il pacchetto](#deploying_package).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-140">[Deploy the package](#deploying_package).</span></span>

<a name="creating_a_collection"></a>

### <a name="create-a-collection"></a><span data-ttu-id="f7a6f-141">Creare una raccolta</span><span class="sxs-lookup"><span data-stu-id="f7a6f-141">Create a collection</span></span>

<span data-ttu-id="f7a6f-142">In questo passaggio selezionare i computer in cui verrà distribuito il pacchetto e il programma e raggrupparli in una raccolta dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-142">In this step, you select the computers to which you will deploy the package and program, and group them into a device collection.</span></span> <span data-ttu-id="f7a6f-143">Per creare una raccolta in Configuration Manager, è possibile usare le regole di appartenenza dirette (dove vengono specificati manualmente i membri della raccolta) oppure regole di query (dove Configuration Manager determina i membri della raccolta in base ai criteri specificati).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-143">To create a collection in Configuration Manager, you can use direct membership rules (where you manually specify the collection members) or query rules (where Configuration Manager determines the collection members based on criteria you specify).</span></span> <span data-ttu-id="f7a6f-144">Per ulteriori informazioni sulle regole di appartenenza, incluse query e regole dirette, vedere [Introduzione alle raccolte in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) nella libreria della documentazione di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-144">For more information about membership rules, including queries and direct rules, see [Introduction to collections in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/introduction-to-collections) in the Configuration Manager Documentation Library.</span></span>

<span data-ttu-id="f7a6f-145">Per creare una raccolta:</span><span class="sxs-lookup"><span data-stu-id="f7a6f-145">To create a collection:</span></span>

1. <span data-ttu-id="f7a6f-146">Nella console di Configuration Manager scegliere **Asset e conformità**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-146">In the Configuration Manager console, choose **Assets and Compliance**.</span></span>

2. <span data-ttu-id="f7a6f-147">Nell'area di lavoro **Asset e conformità** scegliere **Raccolte dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-147">In the **Assets and Compliance** workspace, choose **Device Collections**.</span></span>

3. <span data-ttu-id="f7a6f-148">Nella scheda **Home** del gruppo **Crea** scegliere **Crea raccolta dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-148">On the **Home** tab in the **Create** group, choose **Create Device Collection**.</span></span>

4. <span data-ttu-id="f7a6f-149">Nella pagina **Generale** della **Creazione guidata raccolta dispositivi** digitare un nome per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-149">On the **General** page of the **Create Device Collection Wizard**, enter a name for the collection.</span></span>

5. <span data-ttu-id="f7a6f-150">Scegliere **Sfoglia** per specificare una raccolta di limitazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-150">Choose **Browse** to specify a limiting collection.</span></span>

6. <span data-ttu-id="f7a6f-151">Nella pagina**Regole di appartenenza** scegliere **Aggiungi regola** e quindi **Regola diretta** per aprire la **Creazione guidata regola di appartenenza diretta**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-151">On the **Membership Rules** page, choose **Add Rule**, and then choose **Direct Rule** to open the **Create Direct Membership Rule Wizard**.</span></span> <span data-ttu-id="f7a6f-152">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-152">Choose **Next**.</span></span>

7. <span data-ttu-id="f7a6f-153">Nella pagina **Cerca risorse** scegliere **Risorsa di sistema** nell'elenco **Classe di risorse**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-153">On the **Search for Resources** page, in the **Resource class** list, choose **System Resource**.</span></span> <span data-ttu-id="f7a6f-154">Nell'elenco **Nome attributo** scegliere **Nome**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-154">In the **Attribute name** list, choose **Name**.</span></span> <span data-ttu-id="f7a6f-155">Nel campo **Valore** immettere `%`, quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-155">In the **Value** field, enter `%`, and then choose **Next**.</span></span>

8. <span data-ttu-id="f7a6f-156">Nella pagina **Seleziona risorse** selezionare la casella di controllo per ogni computer a cui si vuole distribuire .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-156">On the **Select Resources** page, select the check box for each computer that you want to deploy the .NET Framework to.</span></span> <span data-ttu-id="f7a6f-157">Scegliere **Avanti** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-157">Choose **Next**, and then complete the wizard.</span></span>

9. <span data-ttu-id="f7a6f-158">Nella pagina **Regole di appartenenza** della **Creazione guidata raccolta dispositivi** scegliere **Avanti** e completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-158">On the **Membership Rules** page of the **Create Device Collection Wizard**, choose **Next**, and then complete the wizard.</span></span>

<a name="creating_a_package"></a>

### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a><span data-ttu-id="f7a6f-159">Creare un pacchetto e un programma per il pacchetto ridistribuibile di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f7a6f-159">Create a package and program for the .NET Framework redistributable package</span></span>

<span data-ttu-id="f7a6f-160">Nei passaggi riportati di seguito viene creato manualmente un pacchetto per il pacchetto ridistribuibile di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-160">The following steps create a package for the .NET Framework redistributable manually.</span></span> <span data-ttu-id="f7a6f-161">Il pacchetto contiene i parametri specificati per l'installazione di .NET Framework e il percorso dal quale il pacchetto verrà distribuito ai computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-161">The package contains the specified parameters for installing the .NET Framework and the location from where the package will be distributed to the target computers.</span></span>

<span data-ttu-id="f7a6f-162">Per creare un pacchetto:</span><span class="sxs-lookup"><span data-stu-id="f7a6f-162">To create a package:</span></span>

1. <span data-ttu-id="f7a6f-163">Nella console di Configuration Manager scegliere **Raccolta software**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-163">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="f7a6f-164">Nell'area di lavoro **Raccolta software** espandere **Gestione applicazioni** e scegliere **Pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-164">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="f7a6f-165">Nella scheda **Home** scegliere **Crea pacchetto** del gruppo **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-165">On the **Home** tab, in the **Create** group, choose **Create Package**.</span></span>

4. <span data-ttu-id="f7a6f-166">Nella pagina **Pacchetto** della **Creazione guidata pacchetto e programma** immettere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7a6f-166">On the **Package** page of the **Create Package and Program Wizard**, enter the following information:</span></span>

    - <span data-ttu-id="f7a6f-167">Nome: `.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="f7a6f-167">Name: `.NET Framework 4.5`</span></span>

    - <span data-ttu-id="f7a6f-168">Produttore: `Microsoft`</span><span class="sxs-lookup"><span data-stu-id="f7a6f-168">Manufacturer: `Microsoft`</span></span>

    - <span data-ttu-id="f7a6f-169">Lingua.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-169">Language.</span></span> `English (US)`

5. <span data-ttu-id="f7a6f-170">Scegliere **Questo pacchetto contiene file di origine**, quindi **Sfoglia** per selezionare la cartella locale o di rete che contiene i file di installazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-170">Choose **This package contains source files**, and then choose **Browse** to select the local or network folder that contains the .NET Framework installation files.</span></span> <span data-ttu-id="f7a6f-171">Dopo aver selezionato la cartella, scegliere **OK**, quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-171">When you have selected the folder, choose **OK**, and then choose **Next**.</span></span>

6. <span data-ttu-id="f7a6f-172">Nella pagina **Tipo di programma** della procedura guidata, scegliere **Programma standard**, quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-172">On the **Program Type** page of the wizard, choose **Standard Program**, and then choose **Next**.</span></span>

7. <span data-ttu-id="f7a6f-173">Nella pagina **Programma** della **Creazione guidata pacchetto e programma** immettere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7a6f-173">On the **Program** page of the **Create Package and Program Wizard**, enter the following information:</span></span>

    1. <span data-ttu-id="f7a6f-174">**Nome:**`.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="f7a6f-174">**Name:** `.NET Framework 4.5`</span></span>

    2. <span data-ttu-id="f7a6f-175">**Riga di comando:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (le opzioni della riga di comando sono descritte nella tabella che segue questi passaggi)</span><span class="sxs-lookup"><span data-stu-id="f7a6f-175">**Command line:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (command-line options are described in the table after these steps)</span></span>

    3. <span data-ttu-id="f7a6f-176">**Esegui:** Scegliere **Nascosto**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-176">**Run:** Choose **Hidden**.</span></span>

    4. <span data-ttu-id="f7a6f-177">**Requisiti per esecuzione programma:** scegliere l'opzione che specifica che il programma può essere eseguito indipendentemente dal fatto che un utente sia connesso o meno.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-177">**Program can run:** Choose the option that specifies that the program can run regardless of whether a user is logged on.</span></span>

8. <span data-ttu-id="f7a6f-178">Nella pagina **Requisiti** scegliere **Avanti** per accettare i valori predefiniti, quindi completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-178">On the **Requirements** page, choose **Next** to accept the default values, and then complete the wizard.</span></span>

<span data-ttu-id="f7a6f-179">Nella tabella seguente vengono descritte le opzioni della riga di comando specificate nel passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-179">The following table describes the command-line options specified in step 7.</span></span>

|<span data-ttu-id="f7a6f-180">Opzione</span><span class="sxs-lookup"><span data-stu-id="f7a6f-180">Option</span></span>|<span data-ttu-id="f7a6f-181">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7a6f-181">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="f7a6f-182">**/q**</span><span class="sxs-lookup"><span data-stu-id="f7a6f-182">**/q**</span></span>|<span data-ttu-id="f7a6f-183">Imposta la modalità non interattiva.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-183">Sets quiet mode.</span></span> <span data-ttu-id="f7a6f-184">Nessun input utente viene richiesto e nessun output viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-184">No user input is required, and no output is shown.</span></span>|
|<span data-ttu-id="f7a6f-185">**/norestart**</span><span class="sxs-lookup"><span data-stu-id="f7a6f-185">**/norestart**</span></span>|<span data-ttu-id="f7a6f-186">Impedisce il riavvio automatico del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-186">Prevents the Setup program from rebooting automatically.</span></span> <span data-ttu-id="f7a6f-187">Se si usa questa opzione, il riavvio del computer deve essere gestito da Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-187">If you use this option, Configuration Manager must handle the computer restart.</span></span>|
|<span data-ttu-id="f7a6f-188">**/chainingpackage** *NomePacchetto*</span><span class="sxs-lookup"><span data-stu-id="f7a6f-188">**/chainingpackage** *PackageName*</span></span>|<span data-ttu-id="f7a6f-189">Specifica il nome del pacchetto che esegue il concatenamento.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-189">Specifies the name of the package that is doing the chaining.</span></span> <span data-ttu-id="f7a6f-190">Questa informazione viene riportata insieme alle altre informazioni sulla sessione di installazione per coloro sono registrati in Microsoft Analisi utilizzo software (CEIP).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-190">This information is reported with other installation session information for those who have signed up for the Microsoft Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="f7a6f-191">Se il nome del pacchetto include spazi, usare le virgolette doppie come delimitatori, ad esempio: **/chainingpackage "Applicazione di concatenamento"**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-191">If the package name includes spaces, use double quotation marks as delimiters; for example: **/chainingpackage "Chaining Product"**.</span></span>|

<span data-ttu-id="f7a6f-192">Questi passaggi creano un pacchetto denominato .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-192">These steps create a package named .NET Framework 4.5.</span></span> <span data-ttu-id="f7a6f-193">Viene distribuita automaticamente un'installazione invisibile all'utente di .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-193">The program deploys a silent installation of the .NET Framework 4.5.</span></span> <span data-ttu-id="f7a6f-194">In un'installazione invisibile, gli utenti non interagiscono con il processo d'installazione e l'applicazione di concatenamento deve acquisire il codice restituito e gestire il riavvio. Vedere [Getting Progress Information from an Installation Package](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100)) (Ottenere informazioni di stato da un pacchetto di installazione).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-194">In a silent installation, users do not interact with the installation process, and the chaining application has to capture the return code and handle rebooting; see [Getting Progress Information from an Installation Package](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100)).</span></span>

<a name="select_dist_point"></a>

### <a name="select-a-distribution-point"></a><span data-ttu-id="f7a6f-195">Selezionare un punto di distribuzione</span><span class="sxs-lookup"><span data-stu-id="f7a6f-195">Select a distribution point</span></span>

<span data-ttu-id="f7a6f-196">Per distribuire il pacchetto e il programma da un server ai computer client, è innanzitutto necessario specificare un sistema di siti come punto di distribuzione e distribuire il pacchetto al punto di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-196">To distribute the package and program to client computers from a server, you must first designate a site system as a distribution point and then distribute the package to the distribution point.</span></span>

<span data-ttu-id="f7a6f-197">Usare i passaggi seguenti per selezionare un punto di distribuzione per il pacchetto di .NET Framework 4.5 creato nella sezione precedente:</span><span class="sxs-lookup"><span data-stu-id="f7a6f-197">Use the following steps to select a distribution point for the .NET Framework 4.5 package you created in the previous section:</span></span>

1. <span data-ttu-id="f7a6f-198">Nella console di Configuration Manager scegliere **Raccolta software**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-198">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="f7a6f-199">Nell'area di lavoro **Raccolta software** espandere **Gestione applicazioni** e scegliere **Pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-199">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="f7a6f-200">Dall'elenco di pacchetti, selezionare il pacchetto **.NET Framework 4.5** creato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-200">From the list of packages, select the package **.NET Framework 4.5** that you created in the previous section.</span></span>

4. <span data-ttu-id="f7a6f-201">Nella scheda **Home** scegliere **Distribuisci contenuto** nel gruppo **Distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-201">On the **Home** tab, in the **Deployment** group, choose **Distribute Content**.</span></span>

5. <span data-ttu-id="f7a6f-202">Nella scheda **Generale** della **Distribuzione guidata contenuto** scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-202">On the **General** tab of the **Distribute Content Wizard**, choose **Next**.</span></span>

6. <span data-ttu-id="f7a6f-203">Nella pagina **Destinazione contenuto** della procedura guidata scegliere **Aggiungi**, quindi **Punto di distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-203">On the **Content Destination** page of the wizard, choose **Add**, and then choose **Distribution Point**.</span></span>

7. <span data-ttu-id="f7a6f-204">Nella finestra di dialogo **Aggiungi punti di distribuzione** selezionare i punti di distribuzione che ospiteranno il pacchetto e il programma, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-204">In the **Add Distribution Points** dialog box, select the distribution point(s) that will host the package and program, and then choose **OK**.</span></span>

8. <span data-ttu-id="f7a6f-205">Completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-205">Complete the wizard.</span></span>

<span data-ttu-id="f7a6f-206">Il pacchetto contiene tutte le informazioni necessarie per distribuire automaticamente .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-206">The package now contains all the information you need to silently deploy the .NET Framework 4.5.</span></span> <span data-ttu-id="f7a6f-207">Prima di distribuire il pacchetto e il programma, verificare che sia stato installato nel punto di distribuzione. vedere la sezione "monitoraggio dello stato dei contenuti" di [monitorare il contenuto distribuito con Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed) nella libreria della documentazione di Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-207">Before you deploy the package and program, verify that it was installed on the distribution point; see the "Content status monitoring" section of [Monitor content you distribute with Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/deploy/configure/monitor-content-you-have-distributed) in the Configuration Manager Documentation Library.</span></span>

<a name="deploying_package"></a>

### <a name="deploy-the-package"></a><span data-ttu-id="f7a6f-208">Distribuire il pacchetto</span><span class="sxs-lookup"><span data-stu-id="f7a6f-208">Deploy the package</span></span>

<span data-ttu-id="f7a6f-209">Per distribuire il pacchetto e il programma di .NET Framework 4.5:</span><span class="sxs-lookup"><span data-stu-id="f7a6f-209">To deploy the .NET Framework 4.5 package and program:</span></span>

1. <span data-ttu-id="f7a6f-210">Nella console di Configuration Manager scegliere **Raccolta software**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-210">In the Configuration Manager console, choose **Software Library**.</span></span>

2. <span data-ttu-id="f7a6f-211">Nell'area di lavoro **Raccolta software** espandere **Gestione applicazioni** e scegliere **Pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-211">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>

3. <span data-ttu-id="f7a6f-212">Nell'elenco di pacchetti selezionare il pacchetto creato denominato **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-212">From the list of packages, select the package you created named **.NET Framework 4.5**.</span></span>

4. <span data-ttu-id="f7a6f-213">Nella scheda **Home** scegliere **Distribuisci** del gruppo **Distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-213">On the **Home** tab, in the **Deployment** group, choose **Deploy**.</span></span>

5. <span data-ttu-id="f7a6f-214">Nella pagina **Generale** della **Distribuzione guidata del software** scegliere **Sfoglia** e selezionare la raccolta creata precedentemente.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-214">On the **General** page of the **Deploy Software Wizard**, choose **Browse**, and then select the collection that you created earlier.</span></span> <span data-ttu-id="f7a6f-215">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-215">Choose **Next**.</span></span>

6. <span data-ttu-id="f7a6f-216">Nella pagina **Contenuto** della procedura guidata, verificare che il punto da cui si vuole distribuire il software sia visualizzato, quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-216">On the **Content** page of the wizard, verify that the point from which you want to distribute the software is displayed, and then choose **Next**.</span></span>

7. <span data-ttu-id="f7a6f-217">Nella pagina**Impostazioni di distribuzione** della procedura guidata, verificare che **Azione** sia impostato su **Installa** e **Scopo** su **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-217">On the **Deployment Settings** page of the wizard, confirm that **Action** is set to **Install**, and **Purpose** is set to **Required**.</span></span> <span data-ttu-id="f7a6f-218">Ciò garantisce che l'installazione del pacchetto software sarà obbligatoria sui computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-218">This ensures that the software package will be a mandatory installation on the targeted computers.</span></span> <span data-ttu-id="f7a6f-219">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-219">Choose **Next**.</span></span>

8. <span data-ttu-id="f7a6f-220">Nella pagina **Pianificazione** della procedura guidata specificare quando si vuole installare .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-220">On the **Scheduling** page of the wizard, specify when you want the .NET Framework to be installed.</span></span> <span data-ttu-id="f7a6f-221">È possibile scegliere **Nuovo** per definire una data e un orario di installazione, specificare che il software dovrà essere installato quando l'utente accede o si disconnette oppure non appena possibile.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-221">You can choose **New** to assign an installation time, or instruct the software to install when the user logs on or off, or as soon as possible.</span></span> <span data-ttu-id="f7a6f-222">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-222">Choose **Next**.</span></span>

9. <span data-ttu-id="f7a6f-223">Nella pagina **Esperienza utente** della procedura guidata, usare i valori predefiniti e scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-223">On the **User Experience** page of the wizard, use the default values and choose **Next**.</span></span>

    > [!WARNING]
    > <span data-ttu-id="f7a6f-224">Nell'ambiente di produzione potrebbero essere impostati criteri che richiedono selezioni diverse per la pianificazione dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-224">Your production environment might have policies that require different selections for the deployment schedule.</span></span> <span data-ttu-id="f7a6f-225">Per informazioni su queste opzioni, vedere [Advertisement Name Properties: Schedule Tab](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb694016%28v=technet.10%29) (Proprietà dei nomi degli annunci: scheda Pianificazione).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-225">For information about these options, see [Advertisement Name Properties: Schedule Tab](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb694016%28v=technet.10%29).</span></span>

10. <span data-ttu-id="f7a6f-226">Nella pagina di **Punti di distribuzione** della procedura guidata usare i valori predefiniti e scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-226">On the **Distribution Points** page of the wizard, use the default values and choose **Next**.</span></span>

11. <span data-ttu-id="f7a6f-227">Completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-227">Complete the wizard.</span></span> <span data-ttu-id="f7a6f-228">È possibile monitorare lo stato di avanzamento della distribuzione nel nodo **Distribuzioni** dell'area di lavoro **Monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-228">You can monitor the progress of the deployment in the **Deployments** node of the **Monitoring** workspace.</span></span>

<span data-ttu-id="f7a6f-229">Il pacchetto verrà ora distribuito alla raccolta di destinazione e l'installazione invisibile all'utente di .NET Framework 4.5 avrà inizio.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-229">The package will now be deployed to the targeted collection and the silent installation of .NET Framework 4.5 will begin.</span></span> <span data-ttu-id="f7a6f-230">Per informazioni sui codici di errore di installazione di .NET Framework 4.5, vedere la sezione [Codici restituiti](#return_codes) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-230">For information about .NET Framework 4.5 installation error codes, see the [Return Codes](#return_codes) section later in this topic.</span></span>

<a name="resources"></a>

## <a name="resources"></a><span data-ttu-id="f7a6f-231">Risorse</span><span class="sxs-lookup"><span data-stu-id="f7a6f-231">Resources</span></span>

<span data-ttu-id="f7a6f-232">Per altre informazioni riguardanti l'infrastruttura per testare la distribuzione del pacchetto ridistribuibile di .NET Framework 4.5, vedere le risorse seguenti.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-232">For more information about the infrastructure for testing the deployment of the .NET Framework 4.5 redistributable package, see the following resources.</span></span>

<span data-ttu-id="f7a6f-233">**Active Directory, DNS, DHCP:**</span><span class="sxs-lookup"><span data-stu-id="f7a6f-233">**Active Directory, DNS, DHCP:**</span></span>

- [<span data-ttu-id="f7a6f-234">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="f7a6f-234">Active Directory Domain Services</span></span>](/windows/desktop/ad/active-directory-domain-services)

- [<span data-ttu-id="f7a6f-235">Domain Name System (DNS)</span><span class="sxs-lookup"><span data-stu-id="f7a6f-235">Domain Name System (DNS)</span></span>](/windows-server/networking/dns/dns-top)

- [<span data-ttu-id="f7a6f-236">Dynamic Host Configuration Protocol (DHCP)</span><span class="sxs-lookup"><span data-stu-id="f7a6f-236">Dynamic Host Configuration Protocol (DHCP)</span></span>](/windows-server/networking/technologies/dhcp/dhcp-top)

<span data-ttu-id="f7a6f-237">**SQL Server 2008:**</span><span class="sxs-lookup"><span data-stu-id="f7a6f-237">**SQL Server 2008:**</span></span>

- <span data-ttu-id="f7a6f-238">[Installazione di SQL Server 2008 (video di SQL Server)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="f7a6f-238">[Installing SQL Server 2008 (SQL Server Video)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/dd299415(v=sql.100))</span></span>

- [<span data-ttu-id="f7a6f-239">SQL Server 2008 Security Overview for Database Administrators (Panoramica della sicurezza di SQL Server 2008 per gli amministratori di database)</span><span class="sxs-lookup"><span data-stu-id="f7a6f-239">SQL Server 2008 Security Overview for Database Administrators</span></span>](https://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)

<span data-ttu-id="f7a6f-240">**System Center 2012 Configuration Manager (punto di gestione, punto di distribuzione):**</span><span class="sxs-lookup"><span data-stu-id="f7a6f-240">**System Center 2012 Configuration Manager (Management Point, Distribution Point):**</span></span>

- [<span data-ttu-id="f7a6f-241">Amministrazione del sito per System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f7a6f-241">Site Administration for System Center 2012 Configuration Manager</span></span>](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg681983%28v=technet.10%29)

- [<span data-ttu-id="f7a6f-242">Configuration Manager Single Site Planning and Deployment (Pianificazione e distribuzione in modalità sito singolo di Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="f7a6f-242">Configuration Manager Single Site Planning and Deployment</span></span>](https://docs.microsoft.com/previous-versions/system-center/configuration-manager-2007/bb680961%28v=technet.10%29)

<span data-ttu-id="f7a6f-243">**Client di System Center 2012 Configuration Manager per computer Windows:**</span><span class="sxs-lookup"><span data-stu-id="f7a6f-243">**System Center 2012 Configuration Manager client for Windows computers:**</span></span>

- [<span data-ttu-id="f7a6f-244">Distribuzione dei client per System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f7a6f-244">Deploying Clients for System Center 2012 Configuration Manager</span></span>](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699391%28v=technet.10%29)

<a name="troubleshooting"></a>

## <a name="troubleshooting"></a><span data-ttu-id="f7a6f-245">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="f7a6f-245">Troubleshooting</span></span>

### <a name="log-file-locations"></a><span data-ttu-id="f7a6f-246">Percorsi dei file di log</span><span class="sxs-lookup"><span data-stu-id="f7a6f-246">Log file locations</span></span>

<span data-ttu-id="f7a6f-247">Durante l'installazione di .NET Framework vengono generati i seguenti file di log:</span><span class="sxs-lookup"><span data-stu-id="f7a6f-247">The following log files are generated during .NET Framework setup:</span></span>

- <span data-ttu-id="f7a6f-248">%temp%\Microsoft .NET Framework *Version* \* . txt</span><span class="sxs-lookup"><span data-stu-id="f7a6f-248">%temp%\Microsoft .NET Framework *version*\*.txt</span></span>
- <span data-ttu-id="f7a6f-249">%temp%\Microsoft .NET Framework *Version* \* . html</span><span class="sxs-lookup"><span data-stu-id="f7a6f-249">%temp%\Microsoft .NET Framework *version*\*.html</span></span>

<span data-ttu-id="f7a6f-250">dove *versione* è la versione di .NET Framework che si sta installando, ad esempio 4.5 o 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-250">where *version* is the version of the .NET Framework that you're installing, such as 4.5 or 4.7.2.</span></span>

<span data-ttu-id="f7a6f-251">È anche possibile specificare la directory in cui vengono scritti i file di log usando l'opzione della riga di comando `/log` nel comando di installazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-251">You can also specify the directory to which log files are written by using the `/log` command-line option in the .NET Framework installation command.</span></span> <span data-ttu-id="f7a6f-252">Per altre informazioni, vedere la [Guida alla distribuzione di .NET Framework per sviluppatori](deployment-guide-for-developers.md#command-line-options).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-252">For more information, see [.NET Framework deployment guide for developers](deployment-guide-for-developers.md#command-line-options).</span></span>

<span data-ttu-id="f7a6f-253">È possibile usare lo [strumento di raccolta dei log](https://www.microsoft.com/download/details.aspx?id=12493) per raccogliere i file di log di .NET Framework e creare un file CAB compresso che riduce le dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-253">You can use the [log collection tool](https://www.microsoft.com/download/details.aspx?id=12493) to collect the .NET Framework log files and to create a compressed cabinet (.cab) file that reduces the size of the files.</span></span>

<a name="return_codes"></a>

### <a name="return-codes"></a><span data-ttu-id="f7a6f-254">Codici restituiti</span><span class="sxs-lookup"><span data-stu-id="f7a6f-254">Return codes</span></span>

<span data-ttu-id="f7a6f-255">Nella tabella seguente vengono elencati i codici più comuni restituiti dal programma di installazione ridistribuibile .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-255">The following table lists the most common return codes from the .NET Framework 4.5 redistributable installation program.</span></span> <span data-ttu-id="f7a6f-256">I codici restituiti sono gli stessi per tutte le versioni del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-256">The return codes are the same for all versions of the installer.</span></span>

<span data-ttu-id="f7a6f-257">Per collegamenti a informazioni dettagliate, vedere la sezione successiva, [Scaricare i codici di errore](#additional_error_codes).</span><span class="sxs-lookup"><span data-stu-id="f7a6f-257">For links to detailed information, see the next section, [Download error codes](#additional_error_codes).</span></span>

|<span data-ttu-id="f7a6f-258">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="f7a6f-258">Return code</span></span>|<span data-ttu-id="f7a6f-259">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7a6f-259">Description</span></span>|
|-----------------|-----------------|
|<span data-ttu-id="f7a6f-260">0</span><span class="sxs-lookup"><span data-stu-id="f7a6f-260">0</span></span>|<span data-ttu-id="f7a6f-261">Installazione completata.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-261">Installation completed successfully.</span></span>|
|<span data-ttu-id="f7a6f-262">1602</span><span class="sxs-lookup"><span data-stu-id="f7a6f-262">1602</span></span>|<span data-ttu-id="f7a6f-263">Installazione annullata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-263">The user canceled installation.</span></span>|
|<span data-ttu-id="f7a6f-264">1603</span><span class="sxs-lookup"><span data-stu-id="f7a6f-264">1603</span></span>|<span data-ttu-id="f7a6f-265">Errore irreversibile durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-265">A fatal error occurred during installation.</span></span>|
|<span data-ttu-id="f7a6f-266">1641</span><span class="sxs-lookup"><span data-stu-id="f7a6f-266">1641</span></span>|<span data-ttu-id="f7a6f-267">Riavvio necessario per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-267">A restart is required to complete the installation.</span></span> <span data-ttu-id="f7a6f-268">Questo messaggio indica l'esito positivo dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-268">This message indicates success.</span></span>|
|<span data-ttu-id="f7a6f-269">3010</span><span class="sxs-lookup"><span data-stu-id="f7a6f-269">3010</span></span>|<span data-ttu-id="f7a6f-270">Riavvio necessario per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-270">A restart is required to complete the installation.</span></span> <span data-ttu-id="f7a6f-271">Questo messaggio indica l'esito positivo dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-271">This message indicates success.</span></span>|
|<span data-ttu-id="f7a6f-272">5100</span><span class="sxs-lookup"><span data-stu-id="f7a6f-272">5100</span></span>|<span data-ttu-id="f7a6f-273">Il computer dell'utente non soddisfa i requisiti di sistema.</span><span class="sxs-lookup"><span data-stu-id="f7a6f-273">The user's computer does not meet system requirements.</span></span>|

<a name="additional_error_codes"></a>

### <a name="download-error-codes"></a><span data-ttu-id="f7a6f-274">Scaricare i codici di errore</span><span class="sxs-lookup"><span data-stu-id="f7a6f-274">Download error codes</span></span>

- <span data-ttu-id="f7a6f-275">[Background Intelligent Transfer Service (BITS) error codes](/windows/desktop/Bits/bits-return-values) (Codici di errore del Servizio trasferimento intelligente in background (BITS))</span><span class="sxs-lookup"><span data-stu-id="f7a6f-275">[Background Intelligent Transfer Service (BITS) error codes](/windows/desktop/Bits/bits-return-values)</span></span>

- [<span data-ttu-id="f7a6f-276">Codici di errore del moniker URL</span><span class="sxs-lookup"><span data-stu-id="f7a6f-276">URL moniker error codes</span></span>](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775145%28v=vs.85%29)

- <span data-ttu-id="f7a6f-277">[WinHttp error codes](/windows/desktop/WinHttp/error-messages) (Codici di errore WinHttp)</span><span class="sxs-lookup"><span data-stu-id="f7a6f-277">[WinHttp error codes](/windows/desktop/WinHttp/error-messages)</span></span>

<span data-ttu-id="f7a6f-278">Altri codici di errore:</span><span class="sxs-lookup"><span data-stu-id="f7a6f-278">Other error codes:</span></span>

- <span data-ttu-id="f7a6f-279">[Windows Installer error codes](/windows/desktop/msi/error-codes) (Codici di errore di Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="f7a6f-279">[Windows Installer error codes](/windows/desktop/msi/error-codes)</span></span>

- <span data-ttu-id="f7a6f-280">[Windows Update Agent result codes](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10)) (Codici restituiti dall'Agente di Windows Update)</span><span class="sxs-lookup"><span data-stu-id="f7a6f-280">[Windows Update Agent result codes](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc720442(v=ws.10))</span></span>

## <a name="see-also"></a><span data-ttu-id="f7a6f-281">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7a6f-281">See also</span></span>

- [<span data-ttu-id="f7a6f-282">Guida alla distribuzione per gli sviluppatori</span><span class="sxs-lookup"><span data-stu-id="f7a6f-282">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)
- [<span data-ttu-id="f7a6f-283">System Requirements</span><span class="sxs-lookup"><span data-stu-id="f7a6f-283">System Requirements</span></span>](../get-started/system-requirements.md)
