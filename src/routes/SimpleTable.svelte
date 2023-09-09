<script lang="ts">
	// @ts-nocheck
	export const tableArr = [
		{ name: 'Hydrogen', symbol: 'H', weight: 1.0079 },
		{ name: 'Helium', symbol: 'He', weight: 4.0026 },
		{ name: 'Lithium', symbol: 'Li', weight: 6.941 },
		{ name: 'Beryllium', symbol: 'Be', weight: 9.0122 },
		{ name: 'Boron', symbol: 'B', weight: 10.811 },
		{ name: 'Carbon', symbol: 'C', weight: 12.0107 },
		{ name: 'Nitrogen', symbol: 'N', weight: 14.0067 },
		{ name: 'Oxygen', symbol: 'O', weight: 15.9994 },
		{ name: 'Fluorine', symbol: 'F', weight: 18.9984 },
		{ name: 'Neon', symbol: 'Ne', weight: 20.1797 }
	];

	const totalWeight = () => {
		let total = 0;
		tableArr.forEach((row: any) => {
			total += row.weight;
		});
		return total;
	};

	const columns = () => {
		const cols = [];
		for (const key in tableArr[0]) {
			cols.push(key);
		}
		return cols;
	};

	console.log(columns());
</script>

<div class="table-container">
	<!-- Native Table Element -->
	<table class="table table-hover">
		<thead>
			<tr>
				{#each columns() as column}
					<th>{column}</th>
				{/each}
			</tr>
		</thead>
		<tbody>
			{#each tableArr as row}
				<tr>
					{#each columns() as column}
						<td>{row[column]}</td>
					{/each}
				</tr>
			{/each}
		</tbody>
		<tfoot>
			<tr>
				<th colspan="3">Calculated Total Weight</th>
				<td>{totalWeight()}</td>
			</tr>
		</tfoot>
	</table>
</div>

