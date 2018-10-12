---
title: Considerazioni su versione e aggiornamento per gli sviluppatori C#
description: L'introduzione delle nuove funzionalità del linguaggio nella libreria può influire sul codice che la usa.
ms.date: 09/19/2018
ms.openlocfilehash: 56685422e2c73dcca25acbdccb3a77a8de9df775
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47199931"
---
# <a name="version-and-update-considerations-for-c-developers"></a><span data-ttu-id="4933d-103">Considerazioni su versione e aggiornamento per gli sviluppatori C#</span><span class="sxs-lookup"><span data-stu-id="4933d-103">Version and update considerations for C# developers</span></span>

<span data-ttu-id="4933d-104">La compatibilità è un obiettivo molto importante quando vengono aggiunte nuove funzionalità al linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="4933d-104">Compatibility is a very important goal as new features are added to the C# language.</span></span> <span data-ttu-id="4933d-105">Nella quasi totalità dei casi, il codice esistente può essere ricompilato con una nuova versione del compilatore senza alcun problema.</span><span class="sxs-lookup"><span data-stu-id="4933d-105">In almost all cases, existing code can be recompiled with a new compiler version without any issue.</span></span>

<span data-ttu-id="4933d-106">Può essere necessaria maggiore attenzione quando si adottano le nuove funzionalità del linguaggio in una libreria.</span><span class="sxs-lookup"><span data-stu-id="4933d-106">More care may be required when you adopt new language features in a library.</span></span> <span data-ttu-id="4933d-107">Si supponga di creare una nuova libreria con le funzionalità disponibili nella versione più recente e di dover verificare che le app create con le versioni precedenti del compilatore siano in grado di usarla.</span><span class="sxs-lookup"><span data-stu-id="4933d-107">You may be creating a new library with features found in the latest version and need to ensure apps built using previous versions of the compiler can use it.</span></span> <span data-ttu-id="4933d-108">In un altro caso, potrebbe essere necessario aggiornare una libreria esistente quando molti utenti non hanno ancora eseguito l'aggiornamento delle versioni.</span><span class="sxs-lookup"><span data-stu-id="4933d-108">Or you may be upgrading an existing library and many of your users may not have upgraded versions yet.</span></span> <span data-ttu-id="4933d-109">Quando si prendono decisioni relative all'adozione di nuove funzionalità, è necessario tenere presenti due tipi di compatibilità: la compatibilità a livello binario e la compatibilità a livello di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="4933d-109">As you make decisions on adopting new features, you'll need to consider two variations of compatibility: source compatible and binary compatible.</span></span>

## <a name="binary-compatible-changes"></a><span data-ttu-id="4933d-110">Modifiche compatibili a livello binario</span><span class="sxs-lookup"><span data-stu-id="4933d-110">Binary compatible changes</span></span>

<span data-ttu-id="4933d-111">Le modifiche apportate a una libreria sono **compatibili a livello binario** quando la libreria aggiornata può essere usata senza ricompilare le applicazioni e le librerie che la usano.</span><span class="sxs-lookup"><span data-stu-id="4933d-111">Changes to your library are **binary compatible** when your updated library can be used without rebuilding applications and libraries that use it.</span></span> <span data-ttu-id="4933d-112">Gli assembly dipendenti non devono essere ricompilati, né sono necessarie modifiche al codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="4933d-112">Dependent assemblies are not required to be rebuilt, nor are any source code changes required.</span></span> <span data-ttu-id="4933d-113">Le modifiche compatibili a livello binario sono anche compatibili a livello di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="4933d-113">Binary compatible changes are also source compatible changes.</span></span>

## <a name="source-compatible-changes"></a><span data-ttu-id="4933d-114">Modifiche compatibili a livello di codice sorgente</span><span class="sxs-lookup"><span data-stu-id="4933d-114">Source compatible changes</span></span>

<span data-ttu-id="4933d-115">Le modifiche apportate a una libreria sono **compatibili a livello di codice sorgente** quando le applicazioni e le librerie che usano la libreria non richiedono modifiche al codice sorgente, ma l'origine deve essere ricompilata con la nuova versione per garantirne il corretto funzionamento.</span><span class="sxs-lookup"><span data-stu-id="4933d-115">Changes to your library are **source compatible** when applications and libraries that use your library do not require source code changes, but the source must be recompiled against the new version to work correctly.</span></span>

## <a name="incompatible-changes"></a><span data-ttu-id="4933d-116">Modifiche incompatibili</span><span class="sxs-lookup"><span data-stu-id="4933d-116">Incompatible changes</span></span>

<span data-ttu-id="4933d-117">Se una modifica non è **compatibile a livello di codice sorgente** né **compatibile a livello binario**, sono necessarie sia modifiche al codice sorgente che la ricompilazione nelle applicazioni e librerie dipendenti.</span><span class="sxs-lookup"><span data-stu-id="4933d-117">If a change is neither **source compatible** nor **binary compatible**, source code changes along with recompilation are required in dependent libraries and applications.</span></span>

## <a name="evaluate-your-library"></a><span data-ttu-id="4933d-118">Valutare la libreria</span><span class="sxs-lookup"><span data-stu-id="4933d-118">Evaluate your library</span></span>

<span data-ttu-id="4933d-119">Questi concetti relativi alla compatibilità interessano le dichiarazioni pubbliche e protette per la libreria, non la relativa implementazione interna.</span><span class="sxs-lookup"><span data-stu-id="4933d-119">These compatibility concepts affect the public and protected declarations for your library, not its internal implementation.</span></span> <span data-ttu-id="4933d-120">Internamente, l'adozione delle nuove funzionalità è sempre **compatibile a livello binario**.</span><span class="sxs-lookup"><span data-stu-id="4933d-120">Adopting any new features internally are always **binary compatible**.</span></span>  

<span data-ttu-id="4933d-121">Le modifiche **compatibili a livello binario**  forniscono una nuova sintassi che genera lo stesso codice compilato per le dichiarazioni pubbliche della sintassi precedente.</span><span class="sxs-lookup"><span data-stu-id="4933d-121">**Binary compatible** changes provide new syntax that generates the same compiled code for public declarations as the older syntax.</span></span> <span data-ttu-id="4933d-122">Ad esempio, la modifica di un metodo in un membro con corpo di espressione è una **modifica compatibile a livello binario**:</span><span class="sxs-lookup"><span data-stu-id="4933d-122">For example, changing a method to an expression-bodied member is a **binary compatible** change:</span></span>

<span data-ttu-id="4933d-123">Codice originale:</span><span class="sxs-lookup"><span data-stu-id="4933d-123">Original code:</span></span>

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

<span data-ttu-id="4933d-124">Nuovo codice:</span><span class="sxs-lookup"><span data-stu-id="4933d-124">New code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="4933d-125">Le modifiche **compatibili a livello di codice sorgente** introducono una sintassi che modifica il codice compilato per un membro pubblico, ma in modo compatibile con i siti di chiamata esistenti.</span><span class="sxs-lookup"><span data-stu-id="4933d-125">**Source compatible** changes introduce syntax that changes the compiled code for a public member, but in a way that is compatible with existing call sites.</span></span> <span data-ttu-id="4933d-126">Ad esempio, la modifica di una firma di un metodo da un parametro per valore a un parametro `in` per riferimento è compatibile a livello di codice sorgente, ma non a livello binario:</span><span class="sxs-lookup"><span data-stu-id="4933d-126">For example, changing a method signature from a by value parameter to an `in` by reference parameter is source compatible, but not binary compatible:</span></span>

<span data-ttu-id="4933d-127">Codice originale:</span><span class="sxs-lookup"><span data-stu-id="4933d-127">Original code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="4933d-128">Nuovo codice:</span><span class="sxs-lookup"><span data-stu-id="4933d-128">New code:</span></span>

```csharp
public double CalculateSquare(in double value) => value * value;
```

<span data-ttu-id="4933d-129">Negli articoli sulle [novità](index.md) è specificato se l'introduzione di una funzionalità che influisce sulle dichiarazioni pubbliche è compatibile a livello di codice sorgente o a livello binario.</span><span class="sxs-lookup"><span data-stu-id="4933d-129">The [What's new](index.md) articles note if introducing a feature that affects public declarations is source compatible or binary compatible.</span></span>