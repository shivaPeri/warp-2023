<script lang="ts">
	import type { PlayerProps } from '$lib';
	import { T } from '@threlte/core';
	import CustomRenderer from './CustomRenderer.svelte';

	export let props: PlayerProps;

	let outlinedMesh: THREE.Mesh;
</script>

<T.Group position={[props.position.x, 0.125, props.position.y]} rotation={[0, -props.heading, 0]}>
	<T.Mesh bind:ref={outlinedMesh}>
		<T.CylinderGeometry args={[1, 1, 0.5]} />
		<T.MeshStandardMaterial color={[0.1, 0.1, 0.1]} />
	</T.Mesh>
	<T.Mesh position={[0.3, 0.25, 0]}>
		<T.CylinderGeometry args={[0.5, 0.5, 0.1]} />
		<T.MeshStandardMaterial color={[0.05, 0.05, 0.05]} />
	</T.Mesh>
</T.Group>

<CustomRenderer selectedMesh={outlinedMesh} />
