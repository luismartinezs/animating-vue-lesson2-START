 <template>
  <div>
    <input v-model="newContact" placeholder="Name" type="text" />
    <button @click="addContact">Add Contact</button>
    <button @click="sortContacts">Sort Contacts</button>

    <transition-group tag="ul" name="slide-up" appear>
      <li v-for="(contact, index) in contacts" :key="index">
        {{ contact }}
      </li>
    </transition-group>
  </div>
</template>
    
    <script>
export default {
  data() {
    return {
      newContact: '',
      contacts: ['Beau Thabeast', 'Cindy Rella', 'Alice Wunderlind'],
    }
  },
  methods: {
    addContact() {
      this.contacts.push(this.newContact)
      this.newContact = ''
    },
    sortContacts() {
      this.contacts.sort()
    },
  },
}
</script>