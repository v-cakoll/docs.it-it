---
ms.openlocfilehash: 1d2e4a058008676c6ea85becebd4bb9220569ef3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621364"
---
### <a name="wpf-spell-checking-in-text-enabled-controls-will-not-work-in-windows-10-for-languages-not-in-the-oss-input-language-list"></a><span data-ttu-id="2858d-101">Il controllo ortografico WPF nei controlli con supporto di testo non funziona in Windows 10 per le lingue non incluse nell'elenco lingue di input del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="2858d-101">WPF spell checking in text-enabled controls will not work in Windows 10 for languages not in the OS's input language list</span></span>

#### <a name="details"></a><span data-ttu-id="2858d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2858d-102">Details</span></span>

<span data-ttu-id="2858d-103">Durante l'esecuzione in Windows 10, il controllo ortografico potrebbe non funzionare per i controlli WPF basati su testo perché le funzionalità di controllo ortografico della piattaforma sono disponibili solo per le lingue presenti nell'elenco delle lingue di input. In Windows 10, quando una lingua viene aggiunta all'elenco di tastiere disponibili, Windows scarica e installa automaticamente una funzione corrispondente nel pacchetto di funzionalità su richiesta (FOD, Feature on Demand) che offre funzionalità di controllo ortografico.</span><span class="sxs-lookup"><span data-stu-id="2858d-103">When running on Windows 10, the spell checker may not work for WPF text-enabled controls because platform spell-checking capabilities are available only for languages present in the input languages list.In Windows 10, when a language is added to the list of available keyboards, Windows automatically downloads and installs a corresponding Feature on Demand (FOD) package that provides spell-checking capabilities.</span></span> <span data-ttu-id="2858d-104">Aggiungendo la lingua all'elenco di lingue di input, il controllo ortografico sarà supportato.</span><span class="sxs-lookup"><span data-stu-id="2858d-104">By adding the language to the input languages list, the spell checker will be supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2858d-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="2858d-105">Suggestion</span></span>

<span data-ttu-id="2858d-106">Tenere presente che per il funzionamento del controllo ortografico in Windows 10 è necessario aggiungere la lingua o il testo da sottoporre a controllo come lingua di input.</span><span class="sxs-lookup"><span data-stu-id="2858d-106">Be aware that the language or text to be spell-checked must be added as an input language for spell-checking to work in Windows 10.</span></span>

| <span data-ttu-id="2858d-107">Nome</span><span class="sxs-lookup"><span data-stu-id="2858d-107">Name</span></span>    | <span data-ttu-id="2858d-108">Valore</span><span class="sxs-lookup"><span data-stu-id="2858d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2858d-109">Scope</span><span class="sxs-lookup"><span data-stu-id="2858d-109">Scope</span></span>   |<span data-ttu-id="2858d-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2858d-110">Edge</span></span>|
|<span data-ttu-id="2858d-111">Version</span><span class="sxs-lookup"><span data-stu-id="2858d-111">Version</span></span>|<span data-ttu-id="2858d-112">4.6</span><span class="sxs-lookup"><span data-stu-id="2858d-112">4.6</span></span>|
|<span data-ttu-id="2858d-113">Type</span><span class="sxs-lookup"><span data-stu-id="2858d-113">Type</span></span>|<span data-ttu-id="2858d-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="2858d-114">Runtime</span></span>|
