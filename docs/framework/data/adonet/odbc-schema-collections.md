---
title: Raccolte di schemi ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772047"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="b8bb3-102">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="b8bb3-102">ODBC Schema Collections</span></span>

<span data-ttu-id="b8bb3-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="b8bb3-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="b8bb3-104">Driver ODBC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="b8bb3-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="b8bb3-105">Il Driver ODBC di Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="b8bb3-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="b8bb3-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="b8bb3-106">Tables</span></span>

- <span data-ttu-id="b8bb3-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="b8bb3-107">Indexes</span></span>

- <span data-ttu-id="b8bb3-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="b8bb3-108">Columns</span></span>

- <span data-ttu-id="b8bb3-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="b8bb3-109">Procedures</span></span>

- <span data-ttu-id="b8bb3-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="b8bb3-110">ProcedureColumns</span></span>

- <span data-ttu-id="b8bb3-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="b8bb3-111">ProcedureParameters</span></span>

- <span data-ttu-id="b8bb3-112">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="b8bb3-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="b8bb3-113">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="b8bb3-113">Tables and Views</span></span>

|<span data-ttu-id="b8bb3-114">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-114">ColumnName</span></span>|<span data-ttu-id="b8bb3-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="b8bb3-116">TABLE_CAT</span></span>|<span data-ttu-id="b8bb3-117">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-117">String</span></span>|
|<span data-ttu-id="b8bb3-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="b8bb3-118">TABLE_SCHEM</span></span>|<span data-ttu-id="b8bb3-119">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-119">String</span></span>|
|<span data-ttu-id="b8bb3-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-120">TABLE_NAME</span></span>|<span data-ttu-id="b8bb3-121">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-121">String</span></span>|
|<span data-ttu-id="b8bb3-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-122">TABLE_TYPE</span></span>|<span data-ttu-id="b8bb3-123">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-123">String</span></span>|
|<span data-ttu-id="b8bb3-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-124">REMARKS</span></span>|<span data-ttu-id="b8bb3-125">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="b8bb3-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="b8bb3-126">Indexes</span></span>

|<span data-ttu-id="b8bb3-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-127">ColumnName</span></span>|<span data-ttu-id="b8bb3-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="b8bb3-129">TABLE_CAT</span></span>|<span data-ttu-id="b8bb3-130">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-130">String</span></span>|
|<span data-ttu-id="b8bb3-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="b8bb3-131">TABLE_SCHEM</span></span>|<span data-ttu-id="b8bb3-132">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-132">String</span></span>|
|<span data-ttu-id="b8bb3-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-133">TABLE_NAME</span></span>|<span data-ttu-id="b8bb3-134">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-134">String</span></span>|
|<span data-ttu-id="b8bb3-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-135">NON_UNIQUE</span></span>|<span data-ttu-id="b8bb3-136">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-136">Int16</span></span>|
|<span data-ttu-id="b8bb3-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="b8bb3-138">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-138">String</span></span>|
|<span data-ttu-id="b8bb3-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-139">INDEX_NAME</span></span>|<span data-ttu-id="b8bb3-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-140">String</span></span>|
|<span data-ttu-id="b8bb3-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-141">TYPE</span></span>|<span data-ttu-id="b8bb3-142">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-142">Int16</span></span>|
|<span data-ttu-id="b8bb3-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="b8bb3-144">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-144">Int16</span></span>|
|<span data-ttu-id="b8bb3-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-145">COLUMN_NAME</span></span>|<span data-ttu-id="b8bb3-146">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-146">String</span></span>|
|<span data-ttu-id="b8bb3-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="b8bb3-147">ASC_OR_DESC</span></span>|<span data-ttu-id="b8bb3-148">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-148">String</span></span>|
|<span data-ttu-id="b8bb3-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="b8bb3-149">CARDINALITY</span></span>|<span data-ttu-id="b8bb3-150">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-150">Int32</span></span>|
|<span data-ttu-id="b8bb3-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="b8bb3-151">PAGES</span></span>|<span data-ttu-id="b8bb3-152">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-152">Int32</span></span>|
|<span data-ttu-id="b8bb3-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-153">FILTER_CONDITION</span></span>|<span data-ttu-id="b8bb3-154">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-154">String</span></span>|
|<span data-ttu-id="b8bb3-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b8bb3-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="b8bb3-156">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-156">String</span></span>|
|<span data-ttu-id="b8bb3-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-158">Byte</span><span class="sxs-lookup"><span data-stu-id="b8bb3-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="b8bb3-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="b8bb3-159">Columns</span></span>

|<span data-ttu-id="b8bb3-160">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-160">ColumnName</span></span>|<span data-ttu-id="b8bb3-161">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="b8bb3-162">TABLE_CAT</span></span>|<span data-ttu-id="b8bb3-163">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-163">String</span></span>|
|<span data-ttu-id="b8bb3-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="b8bb3-164">TABLE_SCHEM</span></span>|<span data-ttu-id="b8bb3-165">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-165">String</span></span>|
|<span data-ttu-id="b8bb3-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-166">TABLE_NAME</span></span>|<span data-ttu-id="b8bb3-167">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-167">String</span></span>|
|<span data-ttu-id="b8bb3-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-168">COLUMN_NAME</span></span>|<span data-ttu-id="b8bb3-169">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-169">String</span></span>|
|<span data-ttu-id="b8bb3-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-170">DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-171">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-171">Int16</span></span>|
|<span data-ttu-id="b8bb3-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-172">TYPE_NAME</span></span>|<span data-ttu-id="b8bb3-173">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-173">String</span></span>|
|<span data-ttu-id="b8bb3-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-174">COLUMN_SIZE</span></span>|<span data-ttu-id="b8bb3-175">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-175">Int32</span></span>|
|<span data-ttu-id="b8bb3-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="b8bb3-177">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-177">Int32</span></span>|
|<span data-ttu-id="b8bb3-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="b8bb3-179">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-179">Int16</span></span>|
|<span data-ttu-id="b8bb3-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="b8bb3-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="b8bb3-181">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-181">Int16</span></span>|
|<span data-ttu-id="b8bb3-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-182">NULLABLE</span></span>|<span data-ttu-id="b8bb3-183">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-183">Int16</span></span>|
|<span data-ttu-id="b8bb3-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-184">REMARKS</span></span>|<span data-ttu-id="b8bb3-185">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-185">String</span></span>|
|<span data-ttu-id="b8bb3-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="b8bb3-186">COLUMN_DEF</span></span>|<span data-ttu-id="b8bb3-187">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-187">String</span></span>|
|<span data-ttu-id="b8bb3-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-189">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-189">Int16</span></span>|
|<span data-ttu-id="b8bb3-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="b8bb3-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="b8bb3-191">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-191">Int16</span></span>|
|<span data-ttu-id="b8bb3-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="b8bb3-193">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-193">Int32</span></span>|
|<span data-ttu-id="b8bb3-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="b8bb3-195">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-195">Int32</span></span>|
|<span data-ttu-id="b8bb3-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-196">IS_NULLABLE</span></span>|<span data-ttu-id="b8bb3-197">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-197">String</span></span>|
|<span data-ttu-id="b8bb3-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b8bb3-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="b8bb3-199">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-199">String</span></span>|
|<span data-ttu-id="b8bb3-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b8bb3-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="b8bb3-201">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-201">String</span></span>|
|<span data-ttu-id="b8bb3-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-203">Byte</span><span class="sxs-lookup"><span data-stu-id="b8bb3-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="b8bb3-204">Procedure</span><span class="sxs-lookup"><span data-stu-id="b8bb3-204">Procedures</span></span>

|<span data-ttu-id="b8bb3-205">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-205">ColumnName</span></span>|<span data-ttu-id="b8bb3-206">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="b8bb3-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="b8bb3-208">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-208">String</span></span>|
|<span data-ttu-id="b8bb3-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="b8bb3-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="b8bb3-210">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-210">String</span></span>|
|<span data-ttu-id="b8bb3-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="b8bb3-212">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-212">String</span></span>|
|<span data-ttu-id="b8bb3-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="b8bb3-214">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-214">Int32</span></span>|
|<span data-ttu-id="b8bb3-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="b8bb3-216">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-216">Int32</span></span>|
|<span data-ttu-id="b8bb3-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="b8bb3-218">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-218">Int32</span></span>|
|<span data-ttu-id="b8bb3-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-219">REMARKS</span></span>|<span data-ttu-id="b8bb3-220">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-220">String</span></span>|
|<span data-ttu-id="b8bb3-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="b8bb3-222">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="b8bb3-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="b8bb3-223">ProcedureColumns</span></span>

|<span data-ttu-id="b8bb3-224">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-224">ColumnName</span></span>|<span data-ttu-id="b8bb3-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="b8bb3-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="b8bb3-227">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-227">String</span></span>|
|<span data-ttu-id="b8bb3-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="b8bb3-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="b8bb3-229">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-229">String</span></span>|
|<span data-ttu-id="b8bb3-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="b8bb3-231">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-231">String</span></span>|
|<span data-ttu-id="b8bb3-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-232">COLUMN_NAME</span></span>|<span data-ttu-id="b8bb3-233">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-233">String</span></span>|
|<span data-ttu-id="b8bb3-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-234">COLUMN_TYPE</span></span>|<span data-ttu-id="b8bb3-235">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-235">Int16</span></span>|
|<span data-ttu-id="b8bb3-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-236">DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-237">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-237">Int16</span></span>|
|<span data-ttu-id="b8bb3-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-238">TYPE_NAME</span></span>|<span data-ttu-id="b8bb3-239">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-239">String</span></span>|
|<span data-ttu-id="b8bb3-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-240">COLUMN_SIZE</span></span>|<span data-ttu-id="b8bb3-241">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-241">Int32</span></span>|
|<span data-ttu-id="b8bb3-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="b8bb3-243">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-243">Int32</span></span>|
|<span data-ttu-id="b8bb3-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="b8bb3-245">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-245">Int16</span></span>|
|<span data-ttu-id="b8bb3-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="b8bb3-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="b8bb3-247">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-247">Int16</span></span>|
|<span data-ttu-id="b8bb3-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-248">NULLABLE</span></span>|<span data-ttu-id="b8bb3-249">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-249">Int16</span></span>|
|<span data-ttu-id="b8bb3-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-250">REMARKS</span></span>|<span data-ttu-id="b8bb3-251">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-251">String</span></span>|
|<span data-ttu-id="b8bb3-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="b8bb3-252">COLUMN_DEF</span></span>|<span data-ttu-id="b8bb3-253">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-253">String</span></span>|
|<span data-ttu-id="b8bb3-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-255">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-255">Int16</span></span>|
|<span data-ttu-id="b8bb3-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="b8bb3-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="b8bb3-257">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-257">Int16</span></span>|
|<span data-ttu-id="b8bb3-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="b8bb3-259">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-259">Int32</span></span>|
|<span data-ttu-id="b8bb3-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="b8bb3-261">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-261">Int32</span></span>|
|<span data-ttu-id="b8bb3-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-262">IS_NULLABLE</span></span>|<span data-ttu-id="b8bb3-263">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-263">String</span></span>|
|<span data-ttu-id="b8bb3-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b8bb3-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="b8bb3-265">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-265">String</span></span>|
|<span data-ttu-id="b8bb3-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b8bb3-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="b8bb3-267">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-267">String</span></span>|
|<span data-ttu-id="b8bb3-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-269">Byte</span><span class="sxs-lookup"><span data-stu-id="b8bb3-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="b8bb3-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="b8bb3-270">ProcedureParameters</span></span>

|<span data-ttu-id="b8bb3-271">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-271">ColumnName</span></span>|<span data-ttu-id="b8bb3-272">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="b8bb3-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="b8bb3-274">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-274">String</span></span>|
|<span data-ttu-id="b8bb3-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="b8bb3-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="b8bb3-276">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-276">String</span></span>|
|<span data-ttu-id="b8bb3-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="b8bb3-278">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-278">String</span></span>|
|<span data-ttu-id="b8bb3-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-279">COLUMN_NAME</span></span>|<span data-ttu-id="b8bb3-280">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-280">String</span></span>|
|<span data-ttu-id="b8bb3-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-281">COLUMN_TYPE</span></span>|<span data-ttu-id="b8bb3-282">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-282">Int16</span></span>|
|<span data-ttu-id="b8bb3-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-283">DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-284">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-284">Int16</span></span>|
|<span data-ttu-id="b8bb3-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-285">TYPE_NAME</span></span>|<span data-ttu-id="b8bb3-286">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-286">String</span></span>|
|<span data-ttu-id="b8bb3-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-287">COLUMN_SIZE</span></span>|<span data-ttu-id="b8bb3-288">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-288">Int32</span></span>|
|<span data-ttu-id="b8bb3-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="b8bb3-290">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-290">Int32</span></span>|
|<span data-ttu-id="b8bb3-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="b8bb3-292">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-292">Int16</span></span>|
|<span data-ttu-id="b8bb3-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="b8bb3-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="b8bb3-294">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-294">Int16</span></span>|
|<span data-ttu-id="b8bb3-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-295">NULLABLE</span></span>|<span data-ttu-id="b8bb3-296">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-296">Int16</span></span>|
|<span data-ttu-id="b8bb3-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-297">REMARKS</span></span>|<span data-ttu-id="b8bb3-298">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-298">String</span></span>|
|<span data-ttu-id="b8bb3-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="b8bb3-299">COLUMN_DEF</span></span>|<span data-ttu-id="b8bb3-300">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-300">String</span></span>|
|<span data-ttu-id="b8bb3-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-302">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-302">Int16</span></span>|
|<span data-ttu-id="b8bb3-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="b8bb3-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="b8bb3-304">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-304">Int16</span></span>|
|<span data-ttu-id="b8bb3-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="b8bb3-306">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-306">Int32</span></span>|
|<span data-ttu-id="b8bb3-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="b8bb3-308">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-308">Int32</span></span>|
|<span data-ttu-id="b8bb3-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-309">IS_NULLABLE</span></span>|<span data-ttu-id="b8bb3-310">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-310">String</span></span>|
|<span data-ttu-id="b8bb3-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="b8bb3-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="b8bb3-312">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-312">String</span></span>|
|<span data-ttu-id="b8bb3-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="b8bb3-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="b8bb3-314">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-314">String</span></span>|
|<span data-ttu-id="b8bb3-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-316">Byte</span><span class="sxs-lookup"><span data-stu-id="b8bb3-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="b8bb3-317">Driver Microsoft ODBC per Oracle</span><span class="sxs-lookup"><span data-stu-id="b8bb3-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="b8bb3-318">Il Driver ODBC di Microsoft SQL Server Oracle supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="b8bb3-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="b8bb3-319">Tabelle</span><span class="sxs-lookup"><span data-stu-id="b8bb3-319">Tables</span></span>

- <span data-ttu-id="b8bb3-320">Colonne</span><span class="sxs-lookup"><span data-stu-id="b8bb3-320">Columns</span></span>

- <span data-ttu-id="b8bb3-321">Procedure</span><span class="sxs-lookup"><span data-stu-id="b8bb3-321">Procedures</span></span>

- <span data-ttu-id="b8bb3-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="b8bb3-322">ProcedureColumns</span></span>

- <span data-ttu-id="b8bb3-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="b8bb3-323">ProcedureParameters</span></span>

- <span data-ttu-id="b8bb3-324">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="b8bb3-324">Views</span></span>

- <span data-ttu-id="b8bb3-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="b8bb3-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="b8bb3-326">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="b8bb3-326">Tables and Views</span></span>

|<span data-ttu-id="b8bb3-327">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-327">ColumnName</span></span>|<span data-ttu-id="b8bb3-328">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="b8bb3-330">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-330">String</span></span>|
|<span data-ttu-id="b8bb3-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-331">TABLE_OWNER</span></span>|<span data-ttu-id="b8bb3-332">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-332">String</span></span>|
|<span data-ttu-id="b8bb3-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-333">TABLE_NAME</span></span>|<span data-ttu-id="b8bb3-334">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-334">String</span></span>|
|<span data-ttu-id="b8bb3-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-335">TABLE_TYPE</span></span>|<span data-ttu-id="b8bb3-336">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-336">String</span></span>|
|<span data-ttu-id="b8bb3-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-337">REMARKS</span></span>|<span data-ttu-id="b8bb3-338">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="b8bb3-339">Colonne</span><span class="sxs-lookup"><span data-stu-id="b8bb3-339">Columns</span></span>

|<span data-ttu-id="b8bb3-340">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-340">ColumnName</span></span>|<span data-ttu-id="b8bb3-341">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="b8bb3-343">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-343">String</span></span>|
|<span data-ttu-id="b8bb3-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-344">TABLE_OWNER</span></span>|<span data-ttu-id="b8bb3-345">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-345">String</span></span>|
|<span data-ttu-id="b8bb3-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-346">TABLE_NAME</span></span>|<span data-ttu-id="b8bb3-347">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-347">String</span></span>|
|<span data-ttu-id="b8bb3-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-348">COLUMN_NAME</span></span>|<span data-ttu-id="b8bb3-349">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-349">String</span></span>|
|<span data-ttu-id="b8bb3-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-350">DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-351">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-351">Int16</span></span>|
|<span data-ttu-id="b8bb3-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-352">TYPE_NAME</span></span>|<span data-ttu-id="b8bb3-353">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-353">String</span></span>|
|<span data-ttu-id="b8bb3-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-354">PRECISION</span></span>|<span data-ttu-id="b8bb3-355">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-355">Int32</span></span>|
|<span data-ttu-id="b8bb3-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-356">LENGTH</span></span>|<span data-ttu-id="b8bb3-357">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-357">Int32</span></span>|
|<span data-ttu-id="b8bb3-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-358">SCALE</span></span>|<span data-ttu-id="b8bb3-359">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-359">Int16</span></span>|
|<span data-ttu-id="b8bb3-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="b8bb3-360">RADIX</span></span>|<span data-ttu-id="b8bb3-361">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-361">Int16</span></span>|
|<span data-ttu-id="b8bb3-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-362">NULLABLE</span></span>|<span data-ttu-id="b8bb3-363">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-363">Int16</span></span>|
|<span data-ttu-id="b8bb3-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-364">REMARKS</span></span>|<span data-ttu-id="b8bb3-365">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-365">String</span></span>|
|<span data-ttu-id="b8bb3-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="b8bb3-367">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="b8bb3-368">Procedure</span><span class="sxs-lookup"><span data-stu-id="b8bb3-368">Procedures</span></span>

|<span data-ttu-id="b8bb3-369">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-369">ColumnName</span></span>|<span data-ttu-id="b8bb3-370">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="b8bb3-372">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-372">String</span></span>|
|<span data-ttu-id="b8bb3-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="b8bb3-374">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-374">String</span></span>|
|<span data-ttu-id="b8bb3-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="b8bb3-376">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-376">String</span></span>|
|<span data-ttu-id="b8bb3-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="b8bb3-378">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-378">Int16</span></span>|
|<span data-ttu-id="b8bb3-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="b8bb3-380">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-380">Int16</span></span>|
|<span data-ttu-id="b8bb3-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="b8bb3-382">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-382">Int16</span></span>|
|<span data-ttu-id="b8bb3-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-383">REMARKS</span></span>|<span data-ttu-id="b8bb3-384">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-384">String</span></span>|
|<span data-ttu-id="b8bb3-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="b8bb3-386">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="b8bb3-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="b8bb3-387">ProcedureColumns</span></span>

|<span data-ttu-id="b8bb3-388">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-388">ColumnName</span></span>|<span data-ttu-id="b8bb3-389">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="b8bb3-391">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-391">String</span></span>|
|<span data-ttu-id="b8bb3-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="b8bb3-393">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-393">String</span></span>|
|<span data-ttu-id="b8bb3-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="b8bb3-395">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-395">String</span></span>|
|<span data-ttu-id="b8bb3-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-396">COLUMN_NAME</span></span>|<span data-ttu-id="b8bb3-397">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-397">String</span></span>|
|<span data-ttu-id="b8bb3-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-398">COLUMN_TYPE</span></span>|<span data-ttu-id="b8bb3-399">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-399">Int16</span></span>|
|<span data-ttu-id="b8bb3-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-400">DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-401">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-401">Int16</span></span>|
|<span data-ttu-id="b8bb3-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-402">TYPE_NAME</span></span>|<span data-ttu-id="b8bb3-403">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-403">String</span></span>|
|<span data-ttu-id="b8bb3-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-404">PRECISION</span></span>|<span data-ttu-id="b8bb3-405">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-405">Int32</span></span>|
|<span data-ttu-id="b8bb3-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-406">LENGTH</span></span>|<span data-ttu-id="b8bb3-407">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-407">Int32</span></span>|
|<span data-ttu-id="b8bb3-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-408">SCALE</span></span>|<span data-ttu-id="b8bb3-409">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-409">Int16</span></span>|
|<span data-ttu-id="b8bb3-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="b8bb3-410">RADIX</span></span>|<span data-ttu-id="b8bb3-411">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-411">Int16</span></span>|
|<span data-ttu-id="b8bb3-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-412">NULLABLE</span></span>|<span data-ttu-id="b8bb3-413">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-413">Int16</span></span>|
|<span data-ttu-id="b8bb3-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-414">REMARKS</span></span>|<span data-ttu-id="b8bb3-415">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-415">String</span></span>|
|<span data-ttu-id="b8bb3-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="b8bb3-416">OVERLOAD</span></span>|<span data-ttu-id="b8bb3-417">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-417">Int32</span></span>|
|<span data-ttu-id="b8bb3-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="b8bb3-419">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="b8bb3-420">Driver ODBC per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="b8bb3-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="b8bb3-421">Oltre alle raccolte di schemi comuni, il driver ODBC per Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8bb3-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="b8bb3-422">Tabelle</span><span class="sxs-lookup"><span data-stu-id="b8bb3-422">Tables</span></span>

- <span data-ttu-id="b8bb3-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="b8bb3-423">Indexes</span></span>

- <span data-ttu-id="b8bb3-424">Colonne</span><span class="sxs-lookup"><span data-stu-id="b8bb3-424">Columns</span></span>

- <span data-ttu-id="b8bb3-425">Procedure</span><span class="sxs-lookup"><span data-stu-id="b8bb3-425">Procedures</span></span>

- <span data-ttu-id="b8bb3-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="b8bb3-426">ProcedureColumns</span></span>

- <span data-ttu-id="b8bb3-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="b8bb3-427">ProcedureParameters</span></span>

- <span data-ttu-id="b8bb3-428">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="b8bb3-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="b8bb3-429">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="b8bb3-429">Tables and Views</span></span>

|<span data-ttu-id="b8bb3-430">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-430">ColumnName</span></span>|<span data-ttu-id="b8bb3-431">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="b8bb3-433">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-433">String</span></span>|
|<span data-ttu-id="b8bb3-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-434">TABLE_OWNER</span></span>|<span data-ttu-id="b8bb3-435">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-435">String</span></span>|
|<span data-ttu-id="b8bb3-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-436">TABLE_NAME</span></span>|<span data-ttu-id="b8bb3-437">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-437">String</span></span>|
|<span data-ttu-id="b8bb3-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-438">TABLE_TYPE</span></span>|<span data-ttu-id="b8bb3-439">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-439">String</span></span>|
|<span data-ttu-id="b8bb3-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-440">REMARKS</span></span>|<span data-ttu-id="b8bb3-441">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="b8bb3-442">Colonne</span><span class="sxs-lookup"><span data-stu-id="b8bb3-442">Columns</span></span>

|<span data-ttu-id="b8bb3-443">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-443">ColumnName</span></span>|<span data-ttu-id="b8bb3-444">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="b8bb3-446">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-446">String</span></span>|
|<span data-ttu-id="b8bb3-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-447">TABLE_OWNER</span></span>|<span data-ttu-id="b8bb3-448">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-448">String</span></span>|
|<span data-ttu-id="b8bb3-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-449">TABLE_NAME</span></span>|<span data-ttu-id="b8bb3-450">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-450">String</span></span>|
|<span data-ttu-id="b8bb3-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-451">COLUMN_NAME</span></span>|<span data-ttu-id="b8bb3-452">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-452">String</span></span>|
|<span data-ttu-id="b8bb3-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-453">DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-454">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-454">Int16</span></span>|
|<span data-ttu-id="b8bb3-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-455">TYPE_NAME</span></span>|<span data-ttu-id="b8bb3-456">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-456">String</span></span>|
|<span data-ttu-id="b8bb3-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-457">PRECISION</span></span>|<span data-ttu-id="b8bb3-458">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-458">Int32</span></span>|
|<span data-ttu-id="b8bb3-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-459">LENGTH</span></span>|<span data-ttu-id="b8bb3-460">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-460">Int32</span></span>|
|<span data-ttu-id="b8bb3-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-461">SCALE</span></span>|<span data-ttu-id="b8bb3-462">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-462">Int16</span></span>|
|<span data-ttu-id="b8bb3-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="b8bb3-463">RADIX</span></span>|<span data-ttu-id="b8bb3-464">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-464">Int16</span></span>|
|<span data-ttu-id="b8bb3-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-465">NULLABLE</span></span>|<span data-ttu-id="b8bb3-466">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-466">Int16</span></span>|
|<span data-ttu-id="b8bb3-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-467">REMARKS</span></span>|<span data-ttu-id="b8bb3-468">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-468">String</span></span>|
|<span data-ttu-id="b8bb3-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="b8bb3-470">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="b8bb3-471">Procedure</span><span class="sxs-lookup"><span data-stu-id="b8bb3-471">Procedures</span></span>

|<span data-ttu-id="b8bb3-472">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-472">ColumnName</span></span>|<span data-ttu-id="b8bb3-473">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="b8bb3-475">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-475">String</span></span>|
|<span data-ttu-id="b8bb3-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="b8bb3-477">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-477">String</span></span>|
|<span data-ttu-id="b8bb3-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="b8bb3-479">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-479">String</span></span>|
|<span data-ttu-id="b8bb3-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="b8bb3-481">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-481">Int16</span></span>|
|<span data-ttu-id="b8bb3-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="b8bb3-483">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-483">Int16</span></span>|
|<span data-ttu-id="b8bb3-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="b8bb3-485">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-485">Int16</span></span>|
|<span data-ttu-id="b8bb3-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-486">REMARKS</span></span>|<span data-ttu-id="b8bb3-487">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-487">String</span></span>|
|<span data-ttu-id="b8bb3-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="b8bb3-489">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="b8bb3-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="b8bb3-490">ProcedureColumns</span></span>

|<span data-ttu-id="b8bb3-491">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-491">ColumnName</span></span>|<span data-ttu-id="b8bb3-492">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="b8bb3-494">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-494">String</span></span>|
|<span data-ttu-id="b8bb3-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="b8bb3-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="b8bb3-496">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-496">String</span></span>|
|<span data-ttu-id="b8bb3-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="b8bb3-498">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-498">String</span></span>|
|<span data-ttu-id="b8bb3-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-499">COLUMN_NAME</span></span>|<span data-ttu-id="b8bb3-500">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-500">String</span></span>|
|<span data-ttu-id="b8bb3-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-501">COLUMN_TYPE</span></span>|<span data-ttu-id="b8bb3-502">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-502">Int16</span></span>|
|<span data-ttu-id="b8bb3-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-503">DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-504">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-504">Int16</span></span>|
|<span data-ttu-id="b8bb3-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-505">TYPE_NAME</span></span>|<span data-ttu-id="b8bb3-506">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-506">String</span></span>|
|<span data-ttu-id="b8bb3-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-507">PRECISION</span></span>|<span data-ttu-id="b8bb3-508">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-508">Int32</span></span>|
|<span data-ttu-id="b8bb3-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-509">LENGTH</span></span>|<span data-ttu-id="b8bb3-510">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-510">Int32</span></span>|
|<span data-ttu-id="b8bb3-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-511">SCALE</span></span>|<span data-ttu-id="b8bb3-512">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-512">Int16</span></span>|
|<span data-ttu-id="b8bb3-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="b8bb3-513">RADIX</span></span>|<span data-ttu-id="b8bb3-514">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-514">Int16</span></span>|
|<span data-ttu-id="b8bb3-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-515">NULLABLE</span></span>|<span data-ttu-id="b8bb3-516">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-516">Int16</span></span>|
|<span data-ttu-id="b8bb3-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-517">REMARKS</span></span>|<span data-ttu-id="b8bb3-518">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-518">String</span></span>|
|<span data-ttu-id="b8bb3-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="b8bb3-519">OVERLOAD</span></span>|<span data-ttu-id="b8bb3-520">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-520">Int32</span></span>|
|<span data-ttu-id="b8bb3-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="b8bb3-522">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="b8bb3-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="b8bb3-523">ProcedureParameters</span></span>

|<span data-ttu-id="b8bb3-524">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="b8bb3-524">ColumnName</span></span>|<span data-ttu-id="b8bb3-525">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="b8bb3-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="b8bb3-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="b8bb3-527">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-527">String</span></span>|
|<span data-ttu-id="b8bb3-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="b8bb3-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="b8bb3-529">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-529">String</span></span>|
|<span data-ttu-id="b8bb3-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="b8bb3-531">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-531">String</span></span>|
|<span data-ttu-id="b8bb3-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-532">COLUMN_NAME</span></span>|<span data-ttu-id="b8bb3-533">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-533">String</span></span>|
|<span data-ttu-id="b8bb3-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-534">COLUMN_TYPE</span></span>|<span data-ttu-id="b8bb3-535">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-535">Int16</span></span>|
|<span data-ttu-id="b8bb3-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-536">DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-537">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-537">Int16</span></span>|
|<span data-ttu-id="b8bb3-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="b8bb3-538">TYPE_NAME</span></span>|<span data-ttu-id="b8bb3-539">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-539">String</span></span>|
|<span data-ttu-id="b8bb3-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-540">COLUMN_SIZE</span></span>|<span data-ttu-id="b8bb3-541">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-541">Int32</span></span>|
|<span data-ttu-id="b8bb3-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="b8bb3-543">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-543">Int32</span></span>|
|<span data-ttu-id="b8bb3-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="b8bb3-545">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-545">Int16</span></span>|
|<span data-ttu-id="b8bb3-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="b8bb3-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="b8bb3-547">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-547">Int16</span></span>|
|<span data-ttu-id="b8bb3-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-548">NULLABLE</span></span>|<span data-ttu-id="b8bb3-549">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-549">Int16</span></span>|
|<span data-ttu-id="b8bb3-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="b8bb3-550">REMARKS</span></span>|<span data-ttu-id="b8bb3-551">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-551">String</span></span>|
|<span data-ttu-id="b8bb3-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="b8bb3-552">COLUMN_DEF</span></span>|<span data-ttu-id="b8bb3-553">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-553">String</span></span>|
|<span data-ttu-id="b8bb3-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="b8bb3-555">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-555">Int16</span></span>|
|<span data-ttu-id="b8bb3-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="b8bb3-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="b8bb3-557">Int16</span><span class="sxs-lookup"><span data-stu-id="b8bb3-557">Int16</span></span>|
|<span data-ttu-id="b8bb3-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="b8bb3-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="b8bb3-559">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-559">Int32</span></span>|
|<span data-ttu-id="b8bb3-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="b8bb3-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="b8bb3-561">Int32</span><span class="sxs-lookup"><span data-stu-id="b8bb3-561">Int32</span></span>|
|<span data-ttu-id="b8bb3-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="b8bb3-562">IS_NULLABLE</span></span>|<span data-ttu-id="b8bb3-563">Stringa</span><span class="sxs-lookup"><span data-stu-id="b8bb3-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="b8bb3-564">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8bb3-564">See also</span></span>

- [<span data-ttu-id="b8bb3-565">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="b8bb3-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
