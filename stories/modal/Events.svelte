<script lang="ts">
  import {
    Button,
    Modal
  } from 'sveltestrap';
  let open = false;
  let status = 'Closed';
  const toggle = () => (open = !open);
</script>

<div>
  <h5>Current state: {status}</h5>
  <Button color="danger" on:click={toggle}>Open Modal</Button>
  <Modal
    body header="Modal title"
    isOpen={open}
    {toggle}
    on:opening={() => status = 'Opening...'}
    on:open={() => status = 'Opened'}
    on:closing={() => status = 'Closing...'}
    on:close={() => status = 'Closed'}>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua.
  </Modal>
</div>
