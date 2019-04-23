---
ms.openlocfilehash: 4cc91e7c6054fdb8e96cecf7120df5b9f25de56c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804288"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="8cb2e-101">I cataloghi MEF implementano IEnumerable e quindi non è più possibile usarli per creare un serializzatore</span><span class="sxs-lookup"><span data-stu-id="8cb2e-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8cb2e-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8cb2e-102">Details</span></span>|<span data-ttu-id="8cb2e-103">A partire da .NET Framework 4.5, i cataloghi MEF implementano IEnumerable e quindi non è più possibile usarli per creare un serializzatore (oggetto <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name>).</span><span class="sxs-lookup"><span data-stu-id="8cb2e-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> object).</span></span> <span data-ttu-id="8cb2e-104">Il tentativo di serializzare un catalogo MEF genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8cb2e-104">Trying to serialize a MEF catalog throws an exception.</span></span>|
|<span data-ttu-id="8cb2e-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="8cb2e-105">Suggestion</span></span>|<span data-ttu-id="8cb2e-106">Non è più possibile usare MEF per creare un serializzatore</span><span class="sxs-lookup"><span data-stu-id="8cb2e-106">Can no longer use MEF to create a serializer</span></span>|
|<span data-ttu-id="8cb2e-107">Ambito</span><span class="sxs-lookup"><span data-stu-id="8cb2e-107">Scope</span></span>|<span data-ttu-id="8cb2e-108">Principale</span><span class="sxs-lookup"><span data-stu-id="8cb2e-108">Major</span></span>|
|<span data-ttu-id="8cb2e-109">Versione</span><span class="sxs-lookup"><span data-stu-id="8cb2e-109">Version</span></span>|<span data-ttu-id="8cb2e-110">4.5</span><span class="sxs-lookup"><span data-stu-id="8cb2e-110">4.5</span></span>|
|<span data-ttu-id="8cb2e-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="8cb2e-111">Type</span></span>|<span data-ttu-id="8cb2e-112">Runtime</span><span class="sxs-lookup"><span data-stu-id="8cb2e-112">Runtime</span></span>|
