# CuteIgniter

CodeIgniter with user authentication, Bootstrap 4 and HTML5 Boilerplate.

## Features

* User authentication
  * Log in/Sign up
  * Forgot Password
  * Change Email
  * Change Password
  * Extend Authenticated_Controller for auth checks
* Mailing list
* Bootstrap 4
  * Alerts with CodeIgniter flashdata
  * Form validation with error styling
* HTML5 Boilerplate

## Examples

Controllers are to extend MY_Controller.

### User
Use the `$this->user` object anywhere to access currently logged in user data

e.g. 
* `$this->user->username`
* `if ($this->user)`

### Forms

For easy use of Bootstrap classes with CodeIgniter validation, inputs can be written like the following:
```
<div class="form-group">
	<label for="email">Email</label>
	<input type="text" name="email" id="email" value="<?php echo set_value('email') ?>" class="form-control <?php echo is_valid('email') ?>">
	<?php echo form_error('email') ?>
</div>
```
Use with CodeIgniter's form validation library
```
$this->form_validation->set_rules('email', 'Email', 'required|valid_email|is_unique[users.email]');
```

### Alerts

CodeIgniter flashdata can be used to display alerts in the form of Bootstrap alerts.
Allowed types are `success`, `error` and `info`.
* In the view - `<?php alerts() ?>`
* Setting the data - `$this->session->set_flashdata('error', 'Invalid login.');`
